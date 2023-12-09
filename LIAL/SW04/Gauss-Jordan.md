Das Gaus-Jordan-Verfahren ist eine Verfahren zur Lösung von [[Lineare Gleichungsysteme|linearen Gleichungssystemen]] es beruht darauf, dass das Gleichungssystem bereits in Zeilenstufenform ist, sprich die [[Gausselimination]] durchgefürht wurde.

Wie bei der [[LU-Zerlegung]] kann der Gauss-Jordan-Algorithmus bei einer gegeben [[Matrizen|Koeffizientenmatrix]] mit verschiedenen [[Vektoren|Lösungsvektoren]] durchgeführt werden.

$$
\begin{align}
Ax &= a \\
Ax &= b \\
Ax &= c \\
: \\
:
\end{align}
$$

## Ablauf
Ist die erweiterte [[Matrizen|Koeffizientenmatrix]] des linearen Gleichungssystems bereits in Zeilenstufenform, ist unser Ziel, in den Spalten oberhalb der Diagonalen Nullen zu erzeugen

- Während wir beim Erzeugen der Zeilenstufenform (Gauss-Verfahren) das lineare Gleichungssystem bzw. dessen erweiterte Koeffizientenmatrix von oben nach unten und von links nach rechts durchgearbeitet haben, gehen wir nun von rechts nach links und von unten nach oben vor.
- Es werden keine Zeilen mehr vertauscht. Der aktuelle [[Gausselimination| Leitkoeffizient]] ist das [[Gausselimination|Pivotelement]].
-  Alle Pivotelemente durch Multiplikation der entsprechenden Zeile mit dem Kehrwert auf den Wert eins gebracht.

### Beispiel
$$A = 
  \left(\begin{array}{rrr|r}
1 & 1 & 1 & 0 \\
4 & 2 & 1 & 1 \\
9 & 3 & 1 & 3
  \end{array}\right)$$
  1. Das Vierfache der ersten Zeile der zweiten abziehen
$$A = 
  \left(\begin{array}{rrr|r}
1 & 1 & 1 & 0 \\
0 & -2 & -3 & 1 \\
9 & 3 & 1 & 3
  \end{array}\right)$$
  2. Das 9 Fach der ersten Zeile der dritten abziehen:
  $$
  A = 
  \left(\begin{array}{rrr|r}
1 & 1 & 1 & 0 \\
0 & -2 & -3 & 1 \\
0 & -6 & -8 & 3
  \end{array}\right)
$$
3. Das 3 Fache der zweiten Zeile der dritten Abziehen
$$
  A = 
  \left(\begin{array}{rrr|r}
1 & 1 & 1 & 0 \\
0 & -2 & -3 & 1 \\
0 & 0 & 1 & 0 \\
  \end{array}\right)$$
  4. Nun das ganze von Unten nach oben: das 3-Fache der dritten Zeile der zweiten addieren.
  $$  A = 
  \left(\begin{array}{rrr|r}
1 & 1 & 1 & 0 \\
0 & -2 & 0  & 1 \\
0 & 0 & 1 & 0 \\
  \end{array}\right)$$
  5. Die dritte Zeile der ersten abziehen:
  $$
    A = 
  \left(\begin{array}{rrr|r}
1 & 1 & 0 & 0 \\
0 & -1 & 0 & 0.5 \\
0 & 0 & 1 & 0 \\
  \end{array}\right)$$
  6. Die zweite Zeile der ersten addieren:
$$  A = 
  \left(\begin{array}{rrr|r}
1 & 0 & 0 & 0.5 \\
0 & -1 & 0 & 0.5 \\
0 & 0 & 1 & 0 \\
  \end{array}\right)$$
  6. Verschönern:
  $$  A = 
  \left(\begin{array}{rrr|r}
1 & 0 & 0 & 0.5 \\
0 & 1 & 0 & -0.5 \\
0 & 0 & 1 & 0 \\
  \end{array}\right)$$


## Invertieren mit Gauss-Jordan
Mit dem Gauss-Jordan lässt sich einfach die [[Invertierte Matrix|Inverse]] einer Matrix definieren.

1. Die Matrix mit einer [[Einheitsmatrix]] ergänzen.

$$
A = 
  \left(\begin{array}{rr|rr}
1 & 3 & 1 & 0 \\
2 & 7 & 0 & 1
  \end{array}\right)
$$
2. Den Gauss Jordan berechnen:
	1. Das 2-Fache der ersten Zeile der zweiten abziehen: 
	$$
		A = 
  \left(\begin{array}{rr|rr}
1 & 3 & 1 & 0 \\
0 & 1 & -2 & 1
  \end{array}\right)
	$$
	2. Das 3-Fache der zweiten Zeile der ersten abziehen:
	$$
	A = 
  \left(\begin{array}{rr|rr}
1 & 0 & 7 & -3 \\
0 & 1 & -2 & 1
  \end{array}\right) $$
  Nun habe wird die Inverse auf der rechten Seite.