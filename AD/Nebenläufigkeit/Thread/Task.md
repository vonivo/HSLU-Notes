>[!info]
>Auszuführende Aufgaben, welche [[Nebenläufigkeit und Parallelität|nebenläufig]] ausgeführt werden, werden **Task** genannt.

Die Definition des Tasks passiert durch die Implementation des [[Interface]] **Runnable**. In der  `run()`-[[Methode]] sind die Anweisungen implementiert.

Damit ein Task ausgeführt werden kann, werden folgende Schritte benötigt:
 1. Erzeugen eines Objektes vom Typ `Runnable`.
 2. Erzeugen eines [[Thread]] Objektes der Klasse `Thread`. (Runnable-Objekt wird dem [[Konstruktor]] mitgegeben.)

>[!warning]
>Mit dem Typen `Runnable` wird klar zwischen dem Programmfluss ([[Thread]]) und der zuerledigenden Aufgabe (**Task**) unterschieden.

## Beispiel
```java
public calss MyTask implements Runnable {
	@Override
	public void run() {...}

	public static void main(String[] args) {
		var myTask = new MyTask();
		var thread = new Thread(myTask, "Thread-Name");
		thread.start();
	}
}
```
