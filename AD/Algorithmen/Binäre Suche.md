Die binäre Suche ist ein Such-[[Algorithmus]] welcher das Suchen eines Elements mit einer [[Komplexität|Zeitkomplexität]] von $O(\log n)$ ermöglicht.

>[!warning]
>Damit die binäre Suche angewandt werden kann, muss die Datenstruktur **sortiert** vorliegen.


## Ablauf
1. Datenelement in der Mitte teilen
2. Aufgrund des Trennelements wird entschieden ob in der oberen oder unteren Hälfte weitergesucht wird. (Vergleich grösser oder kleiner als Trennelement)
3. Algorithmus rekursiv mit der ausgewählten Hälfte wiederholen.
4. Algorithmus endet, wenn Element gefunden wird, oder nur noch ein Element übrig ist.
![[BinarySearch.png]]

