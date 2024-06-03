Das [[Interface]] `Callable` ist eine Alternative zum [[AD/Nebenläufigkeit/Thread/Task|Runnable]] und stellt dabei erweiterte Funktionen zur Verfügung. Unter anderem definiert es die Methode `T call() throws Exception` welche einen Rückgabewert liefert.

Durch das Interface `Callable` kann nun [[Nebenläufigkeit und Parallelität|nebenläufig]](im Gegensatz zum [[AD/Nebenläufigkeit/Thread/Task|Runnable]]):
- Rückgabewerte liefern
- Exceptions handeln.