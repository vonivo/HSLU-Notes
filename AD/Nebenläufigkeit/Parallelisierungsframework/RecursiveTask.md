Die `RecursiveTask` ist eine Art [[AD/Nebenläufigkeit/Thread/Task|Task]] welche bei einem [[Fork-Join-Pool]] benutzt wird und erbt von [[ForkJoinTask]].

Die `RecursiveTask` liefert **einen Rückgabewert.**

## Beispiel
Die Quersumme von  [[Array|Arrays]] lassen sich nach "Teile und Herrsche" berechnen und kann [[Rekursion|rekursiv]] berechnet werden.
**Rekursionsbasis**:
- Zwei Elemente addieren.
**Rekursionsvorschrift**:
1. Teilen der zu berechnenden Folge von Elementen in zwei Hälften.
2. Berchnen der linke un der rechten hälfte
3. Addieren der beiden Resultate.

```java
class SumTask extends RecursiveTask<Integer> {
	private static final THRESHOLD = 5;
	private int[] array;
	private int min;
	private int max;

	public SumTask(int[] array) {      // Öffentlicher Zugangspunkt
		this(array, 0, array.length);
	}

	private SumTask(int[] array, int min, int max) {
		this.array = array;
		this.min = min;
		this.max = max;
	}

	@Override
	protected Integer compute() {
		int sum = 0;
		if ((max - min) <= THRESHOLD) {
			for (int i = min; i < max; i++) {
				sum += this.array[i];
			}
		} else {
			int mid = min + (max - min) / 2;
			var left = new SumTask(min, mid);
			left.fork();                    // frok
			var right = new SumTask(mid, max);
		
			// join
			sum = right.invoke() + left.join();
		}
	}
}
```