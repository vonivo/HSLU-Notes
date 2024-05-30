Virtual Threas ist ein Konstrukt der [[Nebenläufigkeit und Parallelität|Nebenläfuigkeit]] in Java. Sie sind virtuelle Threads welche durch die JVM selbst gehandelt werden und extrem schnell umschalten können.
Dabei Ordnet die JVM selbst die virtuellen Threads den Standard [[Thread|Platform-Threads]] zu, welche wiederum den Betriebssystem-Threads zugewiesen werden..

Virtuelle Threads sind Daemons, dass heisst, sie terminieren, wenn der aufrufende Thread terminiert.

## Ziele
- Skalierung von Serveranwendungen -> im einfachen Thread-pro-Anfrage-Stil.
- Nahezu perfekte Hardwareauslastung.
- Nur minimale Änderungen im Code nötig.

## Anwendungsfall
- Bei Aufgaben welche die meiste Zeit blockiert sind und Abschluss von I/O-Vorgägnen warten.
- Nicht für lang andauernde, CPU-intensive Aufgaben.


## Zuordnung
![[VirtualThreads.png]]

