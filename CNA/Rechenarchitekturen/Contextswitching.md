Ein Thread ist ein Ausführungsstrang eines [[Multicore CPU|Prozesses]]. Wenn ein Prozess beispielsweise bei einem [[CNA/Rechenarchitekturen/Interrupt]] **zwischen Prozessen umschalten** muss, nennt man das **Contextswitching**.
Da aber alle Register gesichert werden müssen, **braucht dies Zeit,** daher kam die Abhilfe mit dem **Multithreading**.

## Multithreading
- Ein Core kann quasi gleichzeitig mehrere Threads abarbeiten.
- Das Betriebssystem erkennt nun nicht mehr die physischen Kerne, sondern die **logischen Kerne** (einzelne Threads)
- Ein Kern mit mehreren Threads besitzt in der Regel ein komplexeres Steuerwerk, dafür aber **mehrere komplette Registersätze**.
- Der **Zustand** des Threads wird **in** einem **[[Speicherzelle|Registersatz]]** gespeichert, was die Zeit um zwischen den Threads zu wechseln extrem verkleinert.
