Optimal-Mismatch basiert auf [[Quicksearch]] und versucht schon beim ersten Vergleich einen Mismatch zu erzielen und so die Zeichenkette noch viel schneller durchzuspringen.

Daher werden die Vergleiche mit dem Pattern so umgestellt, dass zuerst der Unwahrscheinlichste Buchstaben verglichen wird.

Die Wahrscheinlichkeit kann entweder vorher bestimmt werden:
z.B. Deutsch:
- Buchstabe `e` an erster Stelle mit 12 %
- Buchstabe `x`an letzter Stelle mit 0.002 %

## Implementierung
Für die Implementierung wird das Pattern `p` in einer Hilfs-[[OOP/Datenstruktur|Datenstruktur]] so gespeichert, dass, die seltenen Zeichen am Anfang stehen.
![[OptimalMismatch.png]]
Zuerst wird so also mit dem `x` verglichen, danach mit den `t`'s und am Schluss mit dem `e`.
![[OptimalMismatch_2.png]]

Wenn die Statistik fehlt um das Pattern direkt zu "gewichten" können die Datensturkt im Laufe der Suche organisiert werden:
- Wenn ein Vergleich fehlschlägt, wird der Buchstabe des Pattern mit dem ersten vertauscht.
![[OptimalMismach_3.png]]
- Oder der wird mit dem vorderen vertauscht:
![[OptimalMismatch_4.png]]

=> Die [[AD/Algorithmen/Komplexität|Komplexität]] ist gleich wie beim [[Quicksearch]]. In der praxsis ist der Optimal-Mismatch aber **noch schneller**.