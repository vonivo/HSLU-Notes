>[!info]
>Das Fork-Join-Prinzipt zerteilt [[AD/Nebenläufigkeit/Thread/Task|Tasks]] in [[Nebenläufigkeit und Parallelität|nebenläufige]] Aufgaben (Fork) und vereint diese nach der Terminierung wieder (Join).

## Grundprinzip
**Fork** wird von einem (übergeordneten) [[Thread]] aufgerufen, um ein neuen (Kind-)[[Thread]] zu erstellen:
- Der Mutterprozess läuft danach weiter.
- Der Kindprozess startet mit den Berechnungen.
=> Fork schafft Nebenläufigkeit.

**Join** wird weiderum von Eltern- und Kindprozess aufgerufen:
- Kinder rufen implizit join auf, wenn sie beendet wurden.
- Der Mutterprozess wartet auf den "join" des Kindes und fährt danch wieder fort.
=> Join reduziert die Nebenläufigkeit.

### Pattern
```java
function DevideAndConquer(Problem P)
	if P:size < THRESHOLD then
		solfe P sequentially
	else
		fork DevideAndConquer(P1)
		fork DevideAndConquer(P2)
		fork DevideAndConquer(P2)
		join
```

## Kontrollfluss
Der Kontrollfluss des Programms wird an einer spezifischen Stelle in mehrere nebenläufige Prozesse unterteilt und an einer bestimmten Stelle wieder vereinigt.
![[Fork-Join.png]]
Die Vereinigung wird ein Synchronisationspunkt genannt.

Wenn alle Teilaufgabe fertig sind, wird das Programm normal fortgesetzt.

### Parallelisierungsgrad
Der Parallelisierungsgrad wird durch die Grössen **Divider K** und **Combinelevel N** berechnet.

**Divider K** -> Gibt an, in wie viele Subtasks aus einem Task entstehen ( Beispiel: 2)

**Combinelevel N** -> Zeit an, wie viele Synchronisationslevel es benötigt, um die Tasks wieder zu vereinen (Beispiel: 3)

![[Parallelisierungsgrad.png]]

Der Prallelisierungsgrad (Base case) wird durch folgende Formel bestimmt:
$$
K^{N} = \text{Parallelisierungsgrad}
$$
Im Beispiel $2^{3} = 8$.


## Allgemein
- Die Auswahl der Grösse des Basisfalls ist wichtig.
- Die Rekursion sollte genügen in die Tiefe gehen um genu Parallelität zu erreichen.
- Ist die Rekursion zu tief, werden die Tasks durch ds [[Thread]]-Handling dominiert.
- Der Tatsächliche Parallelisierungsgrad hängt von der Anzahl Prozessoren ab.
	Formel: $\frac{\text{Anzahl Daten}}{\text{Cores}}$

## Implementation
### [[AD/Nebenläufigkeit/Thread/Task|Tasks]]
Im Fork-Join-Framework wird die Klasse [[Future]] als Task verwendet. Daraus wird die Klasse [[ForkJoinTask]] abgeleitet, welcher wieder drei mal spezifiziert wird:
- [[RecursiveTask]]
- [[RecursiveAction]]
- [[CountedCompleter]]

![[ForkJoinTasks.png]]
### [[Threadpool]]
Die [[Threadpool|Threadpools]] welche für das Fork-Join verwendet werden sind der `ForkJoinPool` und der `CommonPool`. Der `ForkJoinPool` benutzt das [[Work-Stealing-Verfahren]] wohingegen der `CommonPool` dies nicht benutzt.

#### Methoden
- `void execute(ForkJoinTas<?> task)`
	-> Führt den [[AD/Nebenläufigkeit/Thread/Task|Task]] asynchron aus.
- `<T> T invoke(ForkJoinTask<?> task)`
	-> Startet die Ausführung des Tasks als [[Blockierender Aufruf|blockierender Aufruf]].
	-> `invokeAll()` besitzt die gleiche Semantik, einfach mit einer Liste an Tasks.
- `<T> ForkJoinTask<T> submit(ForkJoinTask<T> task)`
	-> Führt den Task asynchron aus und liefert ein [[Future]] zurück, mit welchen man den Rückgabewert erhalten kann.

#### Beispiel
##### ForkJoinPool
```java
vor pool = new ForkJoinPool();
var task = new SimpleTask();
pool.invoke(task);
```
- Der Pool muss nicht explizit beendet werden da Threads als Deamon laufen.

##### CommonPool
```java
var task = new SimpleTask();
task.invoke();
```
Vorteil: Ressourcen werden geschont, weil nicht benutzte Threads langsam zurückgefahren werden und bei spätere Verwendung wiederhergestellt werden.
