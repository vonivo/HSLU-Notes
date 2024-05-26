Für die Ausführung eines Programms verwendet Java den Call-Stack und den Heap für die Speicherung von Daten.

Bei der Ausführung eines Programms wird meist eine Kette von [[Methode|Funktionen]] aufgerufen und abgearbeitet. Jeder Methodenaufruf erfordert Speicher, weil alle Variablen, welche in der Funktion genutzt werden, gespeichert werden müssen.

Wenn eine Funktion f2 aufgerufen wird, wir dafür ein **Stackframe** erzeugt und auf den Call-Stack gelegt. -> Sprich der Stack wächst um eins, wenn die Funktion f2 fertig ist, wird das Stackframe wieder entfernt.

Beispiel einer [[Rekursion|rekursiven]] Funktion.
![[Callstack.png]]
