>[!Definition]
>Weil die Zeit und das Geld nicht reicht um "Alles" zu testen, muss entschieden werden, **was getestet** wird. Dies muss priorisiert werden.


## Risiko Prioritäts Index
Eine bewährte Methode um zu priorisieren ist die RPI-Methode.

Dazu werdend die Anforderungen im vorhinein zweckmässig gruppiert oder geschnitten.
Im Anschluss werden relevante Bewertungskriterien bestimmt umd die Anforderungen zu bewerten. Folgende Kriterien haben sich oft bewährt:
- Businessrelevanz
- Auffindbarkeit
- Komplexität

### Businessrelevanz
- Wie gross ist die Auswirkung im Fehlerfall.
- was/wie gross könnte der Schaden sein.
- Wie gross ist der Nutzen
- Wie wichtig und kritisch ist es.
- ist es überlebenswichtig.
- Wie schnell breitet sich der Fehler aus.
- wie ansteckend oder virulent ist der Fehler?
- was könnte durch einen Fehler blockiert werden

### Auffindbarkeit
- wie sichtbar ist ein potentieller Fehler
- wie zeigt sich der Fehler
- wie schnell fliegt der Fehler auf
- wie offensichtlich zeigt sich ein Fehlverhalten
- wie gross ist die Wahrscheinlichkeit, dass ein Fehler bemerkt wird
- nach wie vielen Prozessschritten macht sich der Fehler bemerkbar

### Komplexität
- Wie komplex ist die Anforderung?
- Wie komplex ist die Umsetzung?
- Wie vernetzt ist das System
- Wie viele Schnittstellen sind beteilligt?
- Wie komplex ist die angewante Technologie?
- Wieviel unbekannte Grössen, Faktoren, Aspekte sind im Spiel?

### RPI berechnen
1. Bewertet die drei Kriterien mit 1 bis 3
2. Bilde das Produkt der drei Kriterien
3. Bestimme den RPI mithilfe der Tabelle
![[RPI_tabelle.png]]

## Ableiten aus RPI

| Produkt | Priorität | RPI | Testumfang, Testtiefe                                                |
| ------- | --------- | --- | -------------------------------------------------------------------- |
| 27      | very high | 1   | alles in jeder Iteration, sehr gründlich und sehr tief               |
| 18      |           |     | alles pro zwei Iterationen, gründlich und tief                       |
| 12      | high      | 2   | alles pro zwei bis drei Iterationen, wechselnd gründlich/tief        |
| 9       |           |     | wesentliche Abdeckung in mehreren Iteration, gründlich und tief      |
| 8       |           |     | wesentliche Abdeckung über mehrere Iterationen, Wechsel Tiefe/Breite |
| 6       | medium    | 3   | wesentliche Abdeckung verteilt auf mehrere Iterationen               |
| 4       |           |     | Abdeckung wesentlicher Pfade, alternative Pfade wechselnd            |
| 3       |           |     | Abdeckung wesentlciher Pfade, alternative Pfade stichprobenartig     |
| 2       | low       | 4   | nur Abdeckung wesentlicher Pfade                                     |
| 1       | very low  | 5   | stichprobenartige Abdeckung wesentlicher Pfade                       |
