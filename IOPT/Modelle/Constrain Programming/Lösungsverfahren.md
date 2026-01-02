Solver brauchen (generische) Algorithmen zum Lösen der Modelle.

Folgen wird das Lösungsverfahren am [[Graph Coloring]] gezeigt.

**Variablen und Wertebereiche**
- $x_{i}\in \{ r,g,b,v \}$ für alle $i=0,\dots,7$

**Bedingungen**
$x_{i}\neq x_{j}$ für alle Kanten $(i,j)$

1. Können wir inkonsistente Werte in Wertebereichen ausschliessen?
	Nein, also Suche:
	1. Errate Wert einer Variablen (aber sei bereit zum Backtracking)
	2. Hier $x_{2}=r$
	![[CP_Solver_Graph.png]]![[CP_Solver_Baum.png]]
2. Können wir inkonsistente Werte in Wertebereichen ausschliessen?
	Ja: Knoten $1,2,4,5$ können rot nicht annehmen.
3. Weitere Annahme $x_{5}=g$
![[CP_Solver_Graph2.png]]![[CP_Solver_Baum2.png]]
4. Können wir inkonsistente Werte in Wertebereichen ausschliessen?
	Ja, Knoten $4,0,6,7$ können nicht mehr grün werden.
5. Weitere Annahme $x_{4}=b$
![[CP_Solver_Graph3.png]]!![[CP_Solver_Baum3.png]]
6. Weitere Annahme $x_{6}=b$
![[CP_Solver_Graph4.png]]![[CP_Solver_Baum4.png]]
7. Weitere Annahme $x_{0}=v$
![[CP_Solver5.png]]
8. Weitere Annahme $x_{3}=g$
![[CP_Solver6.png]]

**Bemerkung**
- **Domain-Filtering**: Entfernt inkonsistente Werte aus den Wertebereichen der Variablen, basierend auf einzelnen Bedingungen
- **Constraint Propagation**: Propagierung der gefilterten Wertebereiche durch alle Bedingungen und Re-Evaluierung dieser Bedingungen (Filtering) bis es keine Veränderung der Wertebereiche mehr gibt
- **Suche**: Implizit alle möglichen Variablen-Werte-Kombinationen aufzählen; der Suchbaum soll durch Domain-Filtering und Constraint Propagation möglichst klein gehalten werden


## Beispiel 3 Farben
1. $x_{2}=r$
![[CP_Solver_Graph7.png]]![[CP_Solver_Baum7.png]]
2. $x_{5}=g$
3. Wird dies weiter so gemacht, finden wir heraus, dess es nicht möglich ist.



Anstatt Backtracking, hätten wir mehr propagieren können (beim Start)?
![[CP_Solver9.png]]