Gleiches Problem wie in [[Färben|Färben eines Graphen]]

1. Für jeden Knoten $i=0,\dots,n$ sei Variable $x_{i}$ eine Zahl zwischen $0$ und $n$ (Die Farbe des Knotens).
2. Variable $z$ sei die Anzhal eingesetzer Farben, rsp. genauer die nummer der höchsten Farbe.

**Bedingungen**
- Für jede Kante $(i,j)\in E$: $x_{i}\neq x_{j}$
- Stelle sicher dass $z$ die maximale Farbe ist -> $z\geq x_{i}$ für alle $i=0,\dots ,n$

**Zielfunktion**
Minimiere $z$

**Code**
![[CP_GraphColoring_Code1.png]]