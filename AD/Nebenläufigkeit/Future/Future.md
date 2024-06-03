Das [[Interface]] `Future<V>` ist ein Interface, mit dem die Ergebnisrückgabe von [[Nebenläufigkeit und Parallelität|nebenläufigen]] Berechnung einheitlich umgesetzt wird.

Das Interface liefer neben dem Ergebnis auch den Status einer Berechnung.

![[FutureUML 1.png]]

## [[AD/Nebenläufigkeit/Thread/Task|Runnable]] oder [[Callable]]?
### `Future<?> sumbit(Runnable task)`
Wird ein von einem [[Executors|Executor]] erzeugt, welcher nur ein [[AD/Nebenläufigkeit/Thread/Task|Runnable]] enthält, kann die Methoden `isDone()`, `cancle()`, `isCanelled()` verwendend.
Die Methode `get()` ist ein [[Blockierender Aufruf| blockierender Aufruf]] welcher `null` liefert, sobald der Task fertig ist.

### `Future<T> sumbit(Runnable task, T result)`
Bei diesem Aufruf, wird mit `get()` das Objekt `result` unverändert zurückgegeben, wenn der Task ohne Fehler abgearbeitet wurde.

### `Future<T> sumbit(Callable<T> task)`
Mit dieser Version, wird das tatsächliche Resultat der [[Nebenläufigkeit und Parallelität|nebenläufigen]] Berechnung zurückgebeben.

## Methoden
- `get()` -> [[Blockierender Aufruf]] welcher das Ergebnis der Aufgabe zurückliefert.
- `get(Long timeout, TimeUnit unit)` -> Wartet die definierte Zeit auf das Ergebnis. ist das Ergebnis nach Ablauf des Timeouts nicht verfügbar, wird eine `TimeOutException` geworfen.
- `isDone()` -> Liefert den Bearbeitungsstatus zurück.
- `cancel(bool mayInterruptIfRunning)` -> Abbrechen des Tasks.
	- Ist der Task noch nicht gestartet, wird er nicht ausgeführt.
	- Befindet sich der Task in der Bearbeitung, kann ein [[AD/Nebenläufigkeit/Thread/Interrupt|Interrupt]] gesendet werden.
- `isCancelled()` -> Zeigt an ob der Task abgebrochen wurde.

## Beispiel
### Return
Um eine [[Nebenläufigkeit und Parallelität|nebenläufige]] Berechnung mit Rückgabewert zu implementieren, wird folgendes benötigt:
1. Ein [[Callable]] wird erstellt. (Aufgabe mit Rückgabewert).
2. Das [[Callable]] wird über die [[Methode]] `submit()` des [[Executors]] ausgeführt.
3. Die Methode `submit()` liefert als Rückgabewert ein **Future**-Objekt
4. Über das Future-Objekt kann der Rückgabewert und Status abgefragt werden.

```java
Callable<Integer> callable = () -> {
	int sum = 0;
	for (int i = 0; i < 10_000; i++)
		sum += i;
	return sum;
}

var executor = Executors.newCachedThreadPool();
Future<Integer> future = executor.sumbit(callable);  // --> creates Future

future.get() // --> Gets return value of Callable
```
#### Sequenzdiagramm
![[Future_UML_Sequence.png]]

### Exceptions
Beim Aufruf von `submit` wird nicht direkt eine [[Exceptionhandling|Exception]] geworfen.
Die Exception wird erst beim Zugriff auf den Rückgabewert mittel `get()` geworfen und ist dabei vom Typ `ExecutionException`.

```java
var executor = Executors.newCachedThreadPool();
var future = executor.submit(() -> return 100 / 0);

try {
	future.get();
} catch (ExecutionException e) {
	LOG.error(e);
}