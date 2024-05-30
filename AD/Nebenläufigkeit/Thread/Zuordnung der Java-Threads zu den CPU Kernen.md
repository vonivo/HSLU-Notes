Die [[Thread|Threads]] in Java werden 1:1 auf die Threads des [[Betriebssystem]] gemappt.
Danach entscheidet der OS-Scheduler, wann welcher Betriebssystemthread einem [[Contextswitching#Multithreading|Hardware-Thread]] zugewiesen wird.

![[Thread_Mapping.png]]


## Java API
- `Thread.Builder`, `Thread.ofVirtual`, `Thread.ofPlatform`sind neue APIs zum Erstellen von Threads.
- `Thread.startVirtualThread(Runnable)`wird ein virtueller Thread gestartet.
- `Thread.isVirtual` testet, ob ein Thread virtuell ist.