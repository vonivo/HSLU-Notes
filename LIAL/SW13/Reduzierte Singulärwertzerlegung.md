Oft ist $m$ sehr viel grösser als $n$ $(m \gt\gt n)$ oder umgekehrt $n \gt\gt m$, was dazu fürht, dass eine [[Orthogonale Matrix|orthogonale Matrizen]] ebenfalls sehr gross wird: ![[LIAL/SW13/img/SVD.png]]
Falls der [[Rang einer Matrix|Rang]] von $A$ gleich $r$ ist $(r= \operatorname{rang}(A))$, dann ehtält die Matrix $\Sigma$ ebenfalls nur $r$ von Null verschieden [[Singulärwertzerlegung|Signulärwerte]] $\sigma_{1}\ge\sigma_{2}\dots\sigma_{r}\gt 0$.
![[Reduzierte_SVD.png]]

## Beispiel
[[Singulärwertzerlegung]] von der [[Matrizen|Matrix]] $A=\begin{bmatrix}1&1\\-1&-1\end{bmatrix}$ mit dem [[Rang einer Matrix|Rang]] 1.
$$
A = \begin{bmatrix}
	-\frac{1}{\sqrt{ 2 } }  & \frac{1}{\sqrt{ 2 }}\\ 
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }}
\end{bmatrix}\begin{bmatrix}
	2 & 0 \\
 0&0 
\end{bmatrix}\begin{bmatrix}
-\frac{1}{\sqrt{ 2 }} & -\frac{1}{\sqrt{ 2 }} \\
-\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }}
\end{bmatrix}
$$
Wie man sieht existiert nur ein [[Singulärwertzerlegung|Sigulärwert]] welcher von 0 Verschieden ist, daher kann nun eine reduzierte Singulärwertzerlegung durchgeführt werden.
$$
\begin{align}
A &= U_{r}\Sigma_{r}V_{r}^T \\
&=\begin{bmatrix}
-\frac{1}{\sqrt{ 2 }} \\
\frac{1}{\sqrt{ 2 }}
\end{bmatrix}\begin{bmatrix}
2
\end{bmatrix}\begin{bmatrix}
-\frac{1}{\sqrt{ 2 }} & -\frac{1}{\sqrt{ 2 }}
\end{bmatrix}
\end{align}
$$
Wobei sich $r$ bei $U$ auf die Anzahl Spalten bezieht und bei $V$ auf die Anzahl Zeilen.