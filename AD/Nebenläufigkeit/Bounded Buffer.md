Ein bekanntes Problem in der [[Nebenläufigkeit und Parallelität|Nebenläufigkeit]] ist, dass $n$ Produzenten Resultate an $m$ Konsumenten weitergeben muss.
Dazu existiert der **Bounded Buffer** welche die Weitergabe der Resultate über eine Queubewerkstelligt.

-> Falls die Queue im Buffer voll ist, müssen Produzenten warten.
-> Falls die Queue im Buffer leer ist, müssen die Konsumenten warten.

![[Bounded_Buffer.png]]

## Implementation
### Guarded Blocks
Die Implementation eines Bounded Buffers kann mithilfe einer [[Queue#Implementation mit Array|Ringbuffer]] und [[Guarded Block|Guarded Blocks]] gemacht werden.
- Variable `count` entspricht Anazhl an gespeicherten Elementen
- Variable `tail` entspricht dem Index des nächsten Elements
- Variable `head` zeigt auf den nächsten freien Speicherplatz
```java
class BoundedBuffer {
	private final Object lcok = new Object();
	private final Object[] data;
	private int count = 0;
	private int head = 0;
	private int tail = 0;
}
```

#### Daten speichern
```java
public void add(T item) {
	synchronized (lock) {
		while(count == data.length) {
			lock.wait();
		}
		count++;
		data[head] = item;
		head = (head + 1) % data.length;

		if (count == 1) {
			lock.notifyAll();
		}
	}
}
```
- Zuerst wird ein [[Guarded Block]] erstellt, welcher überprüft, ob die Queue voll ist. Wenn ja, wird [[Wait|gewartet]].
- Danach wird dem Ringbuffer ein Element hinzugefügt.
- Am Schluss wird überprüft, ob die Queue vor dem Hinzufügen leer war, wenn ja, werden alle Konsumenten [[Notify|aufgeweckt]].


#### Daten entnehmen
```java
public T remove() {
	synchronized (lock) {
		while(count == 0) {
			lock.wait();
		}
		count--;
		T item = data[tail]
		data[tail] = null;
		tail = (tail + 1) % data.length;

		if (count == data.length - 1) {
			lock.notifyAll();
		}
		return item;
	}
}
```
- Zuerst wird ein [[Guarded Block]] erstellt, welcher überprüft, ob die Queue leer ist. Wenn ja, wird [[Wait|gewartet]].
- Danach wird dem Ringbuffer ein Element entfernt.
- Am Schluss wird überprüft, ob die Queue vor dem Entnehmen leer war, wenn ja, werden alle Produzenten [[Notify|aufgeweckt]].



### Semaphore
Die Implementation eines [[Semaphore]] kann mithilfe einer `ArrayDequeue` und  gemacht werden.
- Variable `putSema` entspricht der Anazhl an Resource um hinzuzufügen
- Variable `takeSeam` entspricht der Anazhl zu entnehmenden Ressourcen
- Variable `queue` die Queue
```java
class BoundedBuffer<T> {
	private Semaphore putSema;
	private Semaphore takeSema;
	private ArrayDequeue<T> queu;

	public BoundedBuffer(int n) {
		this.putSema = new Semaphore(n);
		this.takeSema = new Semaphore();
		this.queu = new ArrayDequeue<>(n);
	}
}
```

#### Daten speichern
```java
public void add(T item) {
	takeSema.acquire();
	synchronized (queue) {
		queue.add(item);
	}
	putSema.release();
}
```
- Zuerst wird darauf gewartet, dass in den Buffer geschrieben werden kann.
- Danach wird in denBuffer geschrieben.
- Am Schluss wird signalisiert, dass nun eine Ressource zur Verfügung steht zum Entnehmen.

#### Daten entnehmen
```java
public T remove() {
	T item = null;
	putSema.acquire();
	synchronized (queue) {
		T = queue.removeLast();
	}
	takeSeam.release();
	return item;
}
```
- Zuerst wird darauf gewartet, dass sich im Buffer mindestens ein Element befindet.
- Danach wird ein Element des Buffers entnommen.
- Am Schluss wird signalisiert, dass der Buffer nun ein freier Platz hat.