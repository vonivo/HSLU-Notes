Das Work-Stealing-Verfahren ist das Rückgrat des [[Fork-Join-Pool]].

Würde man für jeden Task einen neuen [[Thread]] starteten, würde die Anzahl an Threads exponentiell wachsen.

## Prinzip
![[WorkStealing.png]]
Jeder Worker-Thread besitzt eine eigene [[AD/Nebenläufigkeit/Thread/Task|Task]]-Queue.

Wenn nun die Queue eines [[Thread]] leer ist, holt er sich Aufgaben aus der Queue eines anderen.

Dafür wird eine [[Queue|Double-Ended-Queue]] verwendet.