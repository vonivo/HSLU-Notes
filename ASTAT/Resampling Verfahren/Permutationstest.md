Bei einem **Permutationsverfahren** sind zwei oder mehr Stichproben beteiligt, in der Regel die Gruppen in einem A/B- oder anderen Hypothesentest. Permutieren bedeutet, die Reihenfolge einer Menge von gegebenen Werten zu ändern.

Bei einem Permutationstest werden die Resultate der beiden Gruppen A und B in einer "Liste" kombiniert und gemischt, danach werden zufällig Einträge den Gruppen A und B zugeordnet.

Im Anschluss wird getestet wie extreme Ergebnisse der Zufall hervorbringt.

## Ablauf
1. **Kombiniere** der Ereignisse der **verschiedenen Gruppen** in einem Datensatz.
2. **Mische** (zufällig) die kombinierten Daten und ziehe danach für jede Gruppe ohne Zurücklegen eine neue [[Stichprobe]] mit derselben Grösse
3. Berechne die gleiche Statistik für die **Wiederholungsstichprobe** und notiere sie.
4. Wiederhole Schritt 1-3 n Mal.
5. Betrachte den Unterschied in der Menge der permutierten Ergebnisse und dem wahren Ergebnis.
	- Wenn der **beobachtete Unterschied** deutlich _**innerhalb**_ der Menge der **permutierten Unterschiede** liegt, dann haben wir nichts bewiesen - der beobachtete Unterschied liegt im Bereich dessen, was der Zufall hervorbringen könnte.
	- Liegt der **beobachtete Unterschied** jedoch _**ausserhalb**_ des grössten Teils der Menge der **permutierten Unterschiede**, so schliessen wir daraus, dass der Zufall nicht verantwortlich ist. In der Fachsprache heisst das, dass der Unterschied statistisch signifikant ist
	