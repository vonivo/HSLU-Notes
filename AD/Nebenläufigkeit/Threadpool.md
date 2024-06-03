Ein Threadpool ermöglicht die limitierte [[Nebenläufigkeit und Parallelität|nebeläufige]] Ausführung von [[AD/Nebenläufigkeit/Thread/Task|Tasks]].
Dabei werden die auszuführenden Tasks über eine [[Queue]] gespeichert.

Der Threadpool besitzt eine Anzahl an Worker-[[Thread|Threads]] welche die [[AD/Nebenläufigkeit/Thread/Task|Tasks]] nacheinander abarbeiten. Beim Erzeugen des Pools wird festgelegt, wie viele Worker-[[Thread|Threads]] zur Verfügung stehen.
![[ThreadPool.png]]


### Anzahl der Pool-Threads
Die angemessen Anzahl an Worker-[[Thread|Threads]] hängt von der zu bearbeitenden Aufgabe ab.

Für Aufgaben bei denen ein Thread viel Zeit mit warten (z.B. auf I/O-Operation) beschäftigt ist kann folgende Formel verwendet werden:
$$
N_{Threads} =N_{CPU} \times U_{CPU} \times \left( 1 + \frac{W}{C} \right)
$$
- $N_{CPU}$ -> Anzahl der zur Verfügungstehender Kerne
- $U_{CPU}$ -> Auslastung der CPU $0<U_{CPU}<1$ 
- $\frac{W}{C}$ -> Verhätniss zwischen Warte und Rechenzeit

Bei rechenintensieven Aufgaben wird folgende Formel verwendet:
$$
N_{Threads} = N_{CPU} + 1
$$
Also : `Runtime.getRuntime().availableProcessors() + 1`.
## Einfache Implementierung
Eine Einfache und simple implementation von einem ThreadPool.
In der Praxis sollten jedoch die [[Executors]] von Java selbst verwendet werden.
#### Interface
Damit die technische nebenläufige Ausführung von der auszuführenden Aufgabe zu trennen, muss ein [[Interface]] definiert werden, welche einen Typ `Runnable` als Parameter entgegennimmt.
Somit ist eine Entkopplung möglich.
```java
public interface Executor {
	void execute(Runnable task);
}
```

#### ExecutorService

##### Konsturktor
Um den Threadpool zu initialisieren muss eine maximale Kapazität der Anazhal an Aufgaben in der Warteschalange definiert werden und eine Anzahl an Worker.

Im Konstruktor werden die Worker über `activate()` gestartet.
```java
public class PlainThreadPool implements Executor {
	private BoundedBuffer<Runnable> workQueue;
	private int workers;

	public PlainThreadPool(int capacity, int workers) {
		this.workQueue = new BoundedBuffer(capacity);
		this.workers = workers;

		for (int i = 0; i < workers; i++) {
			activate();
		}
	}
}
```

##### Activate
In der Activate-Methode wird jeweils ein Thread gestartet, welcher in einer Endlosschleife die Anzufallenden Task aus dem [[Bounded Buffer]] entfernt und abarbeitet.

Die Methode `setDaemon(true)` stellt sicher, dass der [[Thread]] terminiert wird, sobald der main-Thread terminiert.
```java
private void activate() {
	Runnable runLoop = () -> {
		try {
			while(true) {
				final task = this.workQueue.remove();
				r.run()
			}
		} catch(InterruptedException e) {
			//omited
		}
	}
	var thread = new Thread(runLoop);
	thread.setDaemon(true);
	thread.start();
}
```


##### Execute
Um den Pool mit Aufgaben zu füllen, wird die Methode `execute` verwendet.
```java
public void execute(Runnable task) {
	try {
		this.workQueue.add(task)
	} catch(InterruptedException e) {
		Thread.currentThread().interrupt();
	}
}
```