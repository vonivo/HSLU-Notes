Die `CountedCompleter` ist eine Art [[AD/Nebenläufigkeit/Thread/Task|Task]] welche bei einem [[Fork-Join-Pool]] benutzt wird und erbt von [[ForkJoinTask]].

Die `CountedCompleter` wird eingesetzt, für Aufgaben mit speziellem Warten auf das Ende eines Subtasks (Suche).

## Beispiel
Elemente in eine **nicht sortierten Array** lassen sich nach "Teile und Herrsche" [[Rekursion|rekursiv]] suchen:
**Rekursionsbasis**
- Suchresultat für ein Elment zurückgegen.
**Rekursionsbasis:**
1. Teile der Folge in beliebige Segmente
2. Suchen in allen Segmenten
3. Suchresultat zurückgeben.

Wenn man nur am ersten gefunden Element interresiert ist, kann nach dem ersten Fund die Suche abgebrochen werden.

### Implementation
- `void addToPendingCount(int delta)` -> Erhöht den internen Task-Zähler
- `void tryComplete()` -> Mit dieser Methode wird signalisiert dass ein Task beendet ist.
- `void quietlyCompleteRoot()` -> Signalisiert dem Root-Task, dass ein Ergebnis vorliegt und die aneren Aufgaben abschliessen kann.
- `E getRawResult()` -> Stellt Ergebnis der Berechnung bereit.

```java
class SearchTask extends CountedCompleter<Integer> {
	private static final int SEGMENTS = 5;
	private int key;
	private int[] array;
	private int segmentNo;
	private AtomicInteger result;

	public SearchTask(int key, int[] array) {
		this(null, key, array, -1, new AtomicInteger(-1));
	}

	private SearchTask(CountedCompleter<?> parent, int key, int[] array, int segmentNo, AtomicInteger result) {
		super(parent);
		
		this.key = key;  
		this.array = array;  
		this.segmentNo = segmentNo;  
		this.result = result;
	}

	@Override  
	public Integer getRawResult() {  
	    return result.get();  
	}

	@Override
	protected void compute() {
		if (segmentNo >= 0) {
			int segment = this.array.length / SEGMENTS
			int min = segmentNo * segment
			int max = min + segment;

			// search sequentially
			for (int i = min; i < max; i++) {
				if (i < this.array.length &&
				  array[i] == key &&
				  result.compareAndSet(-1, i)) {
					this.quietlyCompleteRoot();
					break;
				}
			}
		} else {
			this.addToPendigCount(SEGMENTS + 1);
			for (int sNo = 0; i < SEGMENTS + 1; i++) {
				new SearchTask(this, keay, array, sNo, result)
					.fork()
			}
		}
		this.tryComplete();
	}
}
```

