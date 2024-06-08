Die `RecursiveAction` ist eine Art [[AD/Nebenläufigkeit/Thread/Task|Task]] welche bei einem [[Fork-Join-Pool]] benutzt wird und erbt von [[ForkJoinTask]].

Die `RecursiveAction` liefert **kein Rückgabewert.**

## Beispiel
Ein geeigneter Einsatzort für den `RecursiveTask` ist der [[Mergesort]].
Im Nachfolgenden Beispiel wird mit dem [[Mergesort]] bis zur Teilfolge von $n = 1$ gesplittet. Dies sollte in der Praxis nicht so gemacht werden.

### Implementation
```java
class SortTask extends RecursiveAction {   // Klasse erstellen
	private final int THRESHOLD = 5;       // Threshold für seq.
	private final int[] array;             // Zu sortierendes Array
	private int min;                       // Untere grenze
	private int max;                       // Obere grenze

	public SortTask(int[] array) {      // Öffentlicher Zugangspunkt
		this(array, 0, array.length);
	}

	private SortTask(int[] array, int min, int max) {
		this.array = array;
		this.min = min;
		this.max = max;
	}

	@Override
	protected void compute() {
		if (max - min <= THRESHOLD) {
			// sequentiell
		} else {
			int mid = min + (max - min) / 2;
			// Fork & Join
			invokeAll(
				new SortTask(array, min, mid),
				new SortTask(array, mid, max)
			)

			merge(min, mid, max)
		}
	}

	private void merge(int min, int mid, int max) {
		int[] buf = Arrays.copyOfRange(this.array, min, mid);
		int i = 0;
		int j = min;
		int k = mid;
		while (i < buf.length) {
			if (k == max || buf[i] < this.array[k]) {
				this.array[j] = buf[i];
				i++;
			} else {
				this.array[j] = this.array[k];
				k++;
			}
			j++;
		}
	}
}
```

