Das Gauss-Eliminationsverfahren ist ein Standardlösungsverfahren zur Lösung [[Lineare Gleichungsysteme|Linearer Gleichungssysteme]]


Gleichungssysteme und beruht darauf, dass spezielle Gleichungssysteme einfach zu lösen sind.
$$ \left \{ 
	\begin{align} 
	2x + 5y -2z &= -3  \\ 
	  3y + 2z &= 7 \\
	5z &= 10
	\end{align} 
\right. $$
- Aus der letzten Gleichung folgt direkt z 2.
- Setzt man das in die zweite Gleichung ein und löst nach y auf, erhält man y 1.
- Setzt man anschliessend die Werte für x und y in die erste Gleichung ein, und erhält x = -2. Die Lösung des Gleichungssystems ist also (—2, 1, 2).


## Leitkoeffizient und Pivotelemente
Den ersten Eintrag einer Zeile, der nicht verschwindet (nicht 0) nennt man **Leitkoeffizient**. (Hier eingeklammert.)
$$  \left(\begin{array}{rrr|r}
    (2)&5&-2&-3\\
    0&(3)&2&7 \\
    0&0&(5)&10
  \end{array}\right)$$
Steht in einer [[Matrizen |Matrix]] jeder Leitkoeffizient weiter rechts als der Leitkoeffizient in der Zeile darüber, und stehen alle Zeilen Ohne Leitkoeffizient (diejenige mit lauter Nullen) ganz unten, hat die Matrix die Zeilenstufenform. In diesem Fall nennt man die Leitkoeffizienten auch Pivotelemente (hier eingekreist)
  $$  \left(\begin{array}{rrr|r}
    (2)&5&-2&-3\\
    0&(3)&2&7 \\
    0&0&(5)&10\\
    0&0&0&0
  \end{array}\right)$$
  Die Leitkoeffizient müssen nicht zwangsläufig alle auf der Hauptdiagonale stehen:
  $$  \left(\begin{array}{rrrr|r}
    (2)&2&5&-2&-3\\
    0&0&(3)&2&7 \\
    0&0&0&(5)&10\\
    0&0&0&0&0
  \end{array}\right)$$
  Eine quadratische Matrix heisst **obere Dreiecksmatrix**, wennalle Einträge unter der Hauptdiagonale Null sind. Analog dazu definiert man auch eine Untere **Dreicksmatrix**.

## Gauss-Eliminationsverfahren

Beim Gauss-Verfahren geht es darum, lineare Gleichungssysteme so umzuformen, dass Sich eine Zeilenstufenform ergibt. Dann wird durch Rückwärtseinsetzen eine eindeutige Lösung bestimmt, falls das I-GS lösbar ist. Dabei geht man Schritt fiir Schritt vor und wendet in jedem Schritt eine sogenannte elementare Zeilenumformung auf die erweiterte Koeffizientenmatrix an. Es gibt
drei Typen elementarer Zeilenumformungen:
1. Man dar eine Zeile der Erweiterten Koeffizientenmatrix mit einem, der nicht Null ist, multiplizieren:
$$ \left \{ 
	\begin{align} 
	2x +6y &= 1 |(*2)\\ 
	4x - 12y &= 2 \\
	\end{align}
\right. $$
Wird zu:
$$ \left \{ 
	\begin{align} 
	4x +12y &= 2 |(*2)\\ 
	4x - 12y &= 2 \\
	\end{align}
\right. $$
2. Man darf zwei Zeilen der erweiterten Koeffizientenmatrix vertauschen
3. Man darf das Vielfache einer Zeile zu einer anderen addieren:
$$\left \{ 
	\begin{align} 
	4x +12y &= 2 |(*2) \\ 
	4x - 12y &= 2 \\
	\end{align}
\right.$$
$$ \mathrm{I} + \mathrm{II}$$
$$\left \{ 
	\begin{align} 
	4x +12y &= 2 \\ 
	0 - 0 &= 0 \\
	\end{align}
\right.$$
Bei der Gausseleimination wird nun die Matrix so manipuliert, dass sie eine obere Rechte Dreiecksmatrix bildet.
### Beispiel
Die EKM ist: $$\left(\begin{array}{rrr|r}
    6&-1&-1&4\\
    1&1&10&-6 \\
    2&-1&1&-2
  \end{array}\right)$$
  1. Das Pivotelement ist jetzt 6 ist an der richtigen Stelle, aber damit es einfacher zum Rechnen wird, vertauschen wird die Spalte $\mathrm{I}$ mit $\mathrm{II}$.
   
$$\left(\begin{array}{rrr|r}
    1&1&10&-6 \\
    6&-1&-1&4\\
    2&-1&1&-2
  \end{array}\right)$$
  2. Um einen zweiten Leitkoeffizient zu erzeugen, subtrahieren wird das Sechsfache der ersten Zeile von der zweiten.
  $$\left(\begin{array}{rrr|r}
    1&1&10&-6 \\
    0&-7&61&40\\
    2&-1&1&-2
  \end{array}\right)$$
  3. Nun ziehen wir das Doppelte der ersten Zeile der Zweiten ab:
$$
\left(\begin{array}{rrr|r}
    1&1&10&-6 \\
    0&-7&61&40\\
    0&-3&-19&10
  \end{array}\right)
$$
4. Jetzt wird die dritte Zeile mit 7 multipliziert, um das KGV zu schaffen
$$\left(\begin{array}{rrr|r}
    1&1&10&-6 \\
    0&-7&61&40\\
    0&-21&-133&10
  \end{array}\right)$$
  5. Nun wird das 3-fache der zweiten Zeile der dritten Zeile addiert:
  $$\left(\begin{array}{rrr|r}
    1&1&10&-6 \\
    0&-7&61&40\\
    0&0&50&-50
  \end{array}\right)$$
  Jetzt ist die Zeilenstufenform erreicht und mittels Rückwärtseinsetzen kommt man zu folgender Lösung $x=1,y=3, z=-1$
  
  