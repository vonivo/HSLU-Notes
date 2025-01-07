![[Pasted image 20250107191431.png]]

**Vorteile**
- Weniger für Zeit nötig um einen Thread zu erzeugen.
- Wechsel zwischen Threads schneller als zwischen Prozesse
- Kommunikation zwischen Threads durch [[Prozess Kontex]] gegeben.

Im einen modernen OS wird das Scheduling auf Thread ebene gemacht.
Wird ein Prozess unterbrochen/terminiert, werden alle Threads dieses Prozesses unterbrochen/terminiert. 

Threads desselben Prozesses teilen sich:
- Codesegmente
- Datensegmente
- Dateideskriptoren
besitzen jedoch einen eigene:
- Stack
- Codepointer

## Userlevel Thread
Löschen und erstellen von Threads sind teuer Operationen, deshalb gibt es die User-Threads

Die User-Threads werden auf LWP (Lightweight Processes) verteilt. Diese wiederum auf die HW-Threads.
![[Pasted image 20250107192534.png]]