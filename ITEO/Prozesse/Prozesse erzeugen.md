Ein Prozess wird erzeugt, indem er [[Syscall]] **fork()** aufgerufen wird.
Im Kernel passiert folgendes:
1. Alloziere einen freien Platz in der Prozesstabelle für den neuen Prozess
2. Vergib eine eindeutige Prozess-ID für den Child Prozess
3. Mache ine Kopie des Parent-Prozess Image mit Ausnahme vom gesharten Memory
4. Inkrementiere die Zähler für jedes File, das vom Parent benutzt/besessen wird, um anzuzeigen, dass ein zusätzlicher Prozess diese Files auch besitzt.
5. Füge den Child Prozess der "ready to run" Queue hinzu.
6. Retourniere die ID vom Childprozess zum Vaterprozess und den Wert 0 zum child Prozess