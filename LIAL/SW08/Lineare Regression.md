Angenommen, wir haben 3 Datenpunkte in einem 2-Dimensionalem Koordinatensystem. Die erste Koordinate entspricht dem Alter einer Person und die zweite dem Blutdruck:
![[Lineare_Regression.png]]
Gesucht ist nun eine lineare Funktion (Gerade) welche durch die drei Punkte geht:
$$
y = b_{0}+b_{1}x
$$
Daraus ergibt sich folgendes Gleichungssystem $Xb=y$:
$$
 \left \{ 
	\begin{align} 
	c + 0x &=6 \\
    c + x &= 0 \\
    c + 2x &= 0
	\end{align} 
\right.
\space oder
\begin{bmatrix}
1 & 0 \\
1 & 1 \\
1 & 2 
\end{bmatrix}\begin{bmatrix}
c  \\
x
\end{bmatrix} = \begin{bmatrix}
6 \\
0 \\
0
\end{bmatrix}
$$

Unschwer erkennbar ist diese nicht lösbar. Nun geht es darum, eine Gerade so zu ziehen, dass der Fehler $e = y - Xb$ minimal ist:
![[Lineare_Regression_2.png]]

Nur wird diese Gerade mithilfe von Geometrie ermittelt:
![[Lineare_Regression_3.png]]
### Spaltenraum
Rote Fläche -> Spaltenraum $X = \begin{pmatrix}1&0\\1&1\\1&2\end{pmatrix}$ abgelesen aus obiger Gleichung. Ist die Auflistung aller Messwerte in [[Matrizen|Matrixform]] plus eine Spalte aus lauter eines ganz links.

### Lösungsvektor
Grüner Pfeil -> [[Vektoren|Lösungsvektor]] $y=\begin{pmatrix}6\\0\\0\end{pmatrix}$
Vektorielle Auflistung aller Zielgrößen.

### $\hat{y}$ Vorhersage Vektor
Hellgrüner Pfeil -> Zeit die Datenpunkte welche durch die das lineare Regressionsmodell vorhergesagt wurden. $\hat{y} = X \hat{b} = y -e$.

### $\hat{b}$ Modell
Der Vektor $\hat{b}$ beinhaltet die Modellparameter für die Gerade. In diesem Fall $b_0$ und $b_{1}$ aus welchen die Gerade $\hat{y}=b_{0} + b_{1}x$ entsteht.

$\hat{b}$ erhält man, wenn man den Vektor b auf die Spalten der Datenmatrix [[Orthogonale Projektionen|projiziert]].
$\hat{b}=Pb=X(X^TX)^{-1}X^T$b.



