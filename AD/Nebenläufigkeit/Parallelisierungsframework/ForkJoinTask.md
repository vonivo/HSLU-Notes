Der ForkJoinTask ist die Sorte von [[AD/Nebenläufigkeit/Thread/Task|Task]] welche für den [[Fork-Join-Pool]] benutzt wird. Der `ForkJoinTasks` erbt von dem [[Future]] und kann somit ein Rückgabewert generieren.

![[ForkJoinTasks.png]]
Die Konkrete [[Methode]] in welcher die [[Nebenläufigkeit und Parallelität|nebeläufigen]] Berechnungen ausgeführt werden heisst `compute()`. In dieser Methode wird auch die Verzweigung vorgenommen.

Um eine Verzewigung vorzunehemen existieren folgende [[Methode|Methoden]]:
- `fork` -> Task wird asynchron durchgeführt ([[Blockierender Aufruf|nicht blockierend]]).
- `invoke`/`invokeAll` -> Task wird synchron durchgeführt ([[Blockierender Aufruf|blockierend]]).
- `join` -> Holt das Ergebnis eines Tasks ab.
- `get` -> Funktioniert wie [[Future]] wirft im Fehlerfall aber eine `InterruptedException` oder `ExecutionException`.

## Implementationsschema
```java
@Override
protected void compute() {
	if (n <= THRESHOLD) {
		// sequential algorithm
	} else {
		var task1 = new SimpleTask();
		var task2 = new SimpleTask();
		var task3 = new SimpleTask();

		invokeAll(task1, task2, task3);
	}
}
```
