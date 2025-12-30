Beim geometrischen Ansatz wird der Lösungsraum ([[Polytop]]) aufgezeichnet.
Danach wird die Zielfunktion als Gerade innerhalb des Lösungsraumes eingezeichnet und dann parallel verschoben, bis der [[Extremalpunkt]] mit dem höchsten/tiefsten Wert gefunden ist.

**Beispiel Bootsfabrikant**
**Modell**
Maximiere $2400x_{1}+2000x_{2}$ unter den Bedingungen
$$
\begin{align}
4x_{1} & \leq 400 \\
x_{2} & \leq 120  \\
8x_{1}+4x_{2} & \leq 1000 \\
x_{1}&\geq 0 \\
x_{2}&\geq 0
\end{align}
$$
**Lösungsraum**
- Ist ein Polyeder.
- Jeder PUnkt $x$ mit Koordinaten $x_{1},x_{2}$ im Lösungsraum efüllt alle Bedinungen.
- Um eine optimale Lösung zu finden, genügt es die 5 [[Extremalpunkt|Extremalpunkte]] zu betrachten (siehe. [[Minimieren und Maximieren einer konvexen Funktion]])
![[GeometrischerAnsatz.png]]

**Festlegung**
- Für einen gegebenen Wert der Zielfunktion ist die Menge aller Punkte mit diesem Zielfunktionswert eine Gerade
- Die zulässigen Punkte, die diesen Zielfunktionswert haben, liegen auf dieser Geraden und innerhalb des Polyeders
- Vergrössert man den Zielfunktionswert, so verschiebt sich die Gerade parallel
![[GeometrischerAnsatz2.png]]
**Lösungsansatz**
- Verschiebe die Gerade nach oben, solange die Gerade eine nichtleere Schnittmenge mit dem Polyeder hat
- Die Gerade berührt nun das Polyeder an einem optimalen Eckpunk