Das [[Interface]] `Callable` ist eine Alternative zum [[Task|Runnable]] und stellt dabei erweiterte Funktionen zur Verfügung. Unter anderem definiert es die Methode `T call() throws Exception` welche einen Rückgabewert liefert.

Durch das Interface `Callable` kann nun [[Nebenläufigkeit und Parallelität|nebenläufig]](im Gegensatz zum [[Task|Runnable]]):
- Rückgabewerte liefern
- Exceptions handeln.