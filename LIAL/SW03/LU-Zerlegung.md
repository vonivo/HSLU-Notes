Wir wollen die [[Matrizen|Matrix]] $A=\begin{pmatrix}2&1\\8&7\end{pmatrix}$ in [[Gausselimination|Zeilenstufenform]] bringen.
Um $a_{21}$ verschwinden zu lassen, subtrahieren wir das Vierfache der ersten Zeile von der zweiten Zeile. (Analog [[Gausselimination]]).

## Eliminationsmatrix

Dieses Verfahren kann auch mittels einer [[Matrixmultiplikation]] erreicht werden:
$$
\begin{pmatrix}
1 & 0 \\
-4 & 1
\end{pmatrix} *
\begin{pmatrix}
2 & 1 \\
8 & 7
\end{pmatrix} = 
\begin{pmatrix}
2 & 1 \\
0 & 3
\end{pmatrix}
$$
Die Matrix $\begin{pmatrix}1&0\\-4&1\end{pmatrix}$ nennt man Eliminationsmatrix $E_{21}$. Der Index $_{21}$ gibt an, dass der Eintrag $a_{21}$ durch Multiplikation eliminiert wurde.
## Beispiel
Die Idee der LU-Zerlegung einer Matrix $A \in \mathbb{R}^{3*3}$ ist die Einträge $a_{21}$, $a_{31}$ und $a_{32}$ durch eine Multiplikation mit geeigneten Matrizen $E_{21}$, $E_{31}$ und $E_{32}$ verschwinden zu lassen.

Die Matrix $E_{32}E_{31}E_{21}A$ ist dann in Zeilenstufenform. (Wie bei der Gausselimination)

## Ablauf
$$\begin{align} \\
E_{32}*E_{31}*E_{21}*A &= U \\
(E_{32}*E_{31}*E_{21})^{-1} * E_{32}*E_{31}*E_{21}*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
((E_{32}*E_{31}*E_{21})^{-1} * E_{32}*E_{31}*E_{21})*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
(E_{21}^{-1}*E_{31}^{-1}*E_{32}^{-1} * E_{32}*E_{31}*E_{21})*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
(E_{21}^{-1}*E_{31}^{-1}*I*E_{31}*E_{21})*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
(E_{21}^{-1}*E_{31}^{-1}*E_{31}*E_{21})*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
(E_{21}^{-1}*I*E_{21})*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
(E_{21}^{-1}*E_{21})*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
I*A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
A &= (E_{32}*E_{31}*E_{21})^{-1} * U \\
A &= E_{21}^{-1}*E_{31}^{-1}*E_{32}^{-1} * U \\
A &= L*U
\end{align}
$$
Jeder Eliminationsschritt hat eine Inverse.

Die LU-Zerlegung kann auch mit einer [[Permuationsmatrix]] ausgeführt werden: $PA =LU$.
### Beispiel Permutation
$$
A = \begin{pmatrix}
0 & 1 & 1 \\
1 & 2 & 1 \\
2 & 7 & 9
\end{pmatrix}
$$
Das Pivot-Element darf nicht $0$ sein:
$$
\begin{pmatrix}
0 & 1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
0 & 1 & 1 \\
1 & 2 & 1 \\
2 & 7 & 9
\end{pmatrix} = 
\begin{pmatrix}
1 & 2 & 1 \\
0 & 1 & 1 \\
2 & 7 & 9
\end{pmatrix}
$$

## Lösen eines Gleichungssystems

Das ursprüngliche [[Lineare Gleichungsysteme|lineare Gleichungssystem]] $Ax = b$  folgt vereinfacht:  
$$ \begin{align}
Ax &= b \\
A &= LU \\
(LU)x &= b
\end{align}$$
Wobei $A$ die Koeffizientenmatrix darstellt, x die Unbekannten darstellt $x=\begin{pmatrix}x_{1}\\ x_{2}\\x_{3}\end{pmatrix}$ und b den [[Vektoren|Lösungsvektor]] $b= \begin{pmatrix} 1\\ 3\\ 4\end{pmatrix}$.
Nun wird folgendes definiert:
$$\begin{align}
Ly &= b \\
Ux &= y
\end{align}$$
Danach wird das Gleichungssystem $L\vec{y}=\vec{b}$ gelöst.
Mit der nun erhaltenen Lösung von $\vec{y}$ kann das Gleichungssystem $U\vec{x} = \vec{y}$ gelöst werden und man erhält die Lösung für $\vec{x}$ welche das ganze Gleichungssystem löst.


## Anwendung
Mit der LU-Zerlegung kann ein Gleichungssystem mehrmals effizient gelöst werden, bei welchem sich nur der Lösungsvektor $\vec{b}$ ändert. Da $L$ und $U$ nur einmal berechnet werden müssen, kann danach einfach nur eingesetzt werden.
Im Gegensatz zur [[Gausselimination]] muss nur einmal eine "Aufwändige" Berechnung gemacht werden.




>[!warning] LU-Zerlegung mit Permutation
>Werden bei einer LU-Zerlegung die Zeilen mit einer Permutationsmatrix $P$ vertausch, müssen auch die Zeilen des Lösungsvektors $\vec{b}$ vertauscht werden












