Java bietet eine Reihe an Executors an, welche verschiedene [[Threadpool|Threadpools]] umsetzen. Um diese Pools zu erzeugen, existieren verschieden Factory-Methoden.

In Java gibt es drei verschiedene Executor-Typen:
- `ThreadPoolExecutor`
- `ScheduledThreadPoolExecutor`
- `ForkJoinPool` (vgl. [[Fork-Join-Pool]])


## Implementation
### CachedThreadPool
Der `CachedThreadPool`wird über `Executors.newCachedThreadPool()` erzeugt.
Dieser Pool erzeugt bei Bedarf neue Worker-[[Thread|Threads]]. Sobald ein [[AD/Nebenläufigkeit/Thread/Task]] benndet ist, wird der [[Thread]] dazu für 60 Sekunden gecached und wenn möglich wieder verwendet.

### VirtualThreadPerTaskExecutor
Der `VirtualThreadPerTaskExecutor` wird über `Executors.newVirtualThreadPerTaskExecutor()` erzeugt.
Dieser Pool erstellt für jednen [[AD/Nebenläufigkeit/Thread/Task]] einen eigenen [[Virtual Threads|virtuellen Thread]]. Die maximale Anzahl an virtuellen Threads ist dabei unbegrenzt.

### FixedThreadPool
Der `FixedThreadPool` wird über `Executors.newFixedThreadPool(int nThreads)` erzeugt.
Erstellt die über `nThreads` definiert Anzahl an Threads, die Anzahl an [[AD/Nebenläufigkeit/Thread/Task|Tasks]] in der Queue ist unbegrenzt.
Stirbt ein Thread wird ein neuer erzeugt.

### SingleThreadExecutor
Der `SingleThreadExecutor` wird über `Executors.newSingleThreadExecutor()` erzeugt.
Dieser Pool stellt nur einen Thread zur Verfügung und es wird garantiert, dass die [[Queue]] sequenziell abgearbeitet wird.

### ScheduledThreadPool
Der `ScheduledThreadPool` wird über `Executors.newScheduledThreadPool(int corePoolSize)` erzeugt.
Dieser Pool führt ausgaben nach einer definierten Verzögerung oder periodisch aus.

### Klassenhierarchie
![[Executor_UML.png]]

## Empfehlungen
- Bei vielen, einfachen und eher kurzen [[AD/Nebenläufigkeit/Thread/Task|Tasks]] einen [[Threadpool]] benutzt. Dies macht die Applikation einfach zu handhaben und effizienter.
- Bei abhängigen Aufgaben sind [[Synchronized|Synchronisationene]] notwendig.