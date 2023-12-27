Die Singulärwertzerlegung (Single Value Decomposition, SVD) zerlegt jede beliebige $m \times n$-[[Matrizen|Matrix]] $A$ in drei Matrizen $U, \Sigma, V$.
$$
\begin{align}
A &= U\Sigma V^T \\
&=\sigma_{1}u_{1}v_{1}^{T} + \sigma_{2}u_{2}v_{2}^{T}+\dots+\sigma_{n}u_{n}v_{n}^{T}
\end{align}
$$
Dabei gilt:
- $U$ $=>$ eine [[Orthogonale Matrix|orthogonale]] $m \times m$-Matrix ($U^TU=I$, d. h. $U^{-1}=U^T$)
- $\Sigma$ $=>$ eine $m \times n$-[[Diagonalmatrix]] mit den Singulärwerten auf der Diagonale.
- $V$ $=>$ eine [[Orthogonale Matrix|orthogonale]] $n \times n$-Matrix ($V^TV=I$, d. h. $V^{-1}=V^T$)
![[LIAL/SW12/img/SVD.png]]
>[!warning]
>Die **Singulärwerte** $\sigma_{i}$ sind positiv und geordnet: $\sigma_1 \ge\sigma_{2}\dots\ge\sigma_{n}\ge 0$

## Vorgehen
Um die einzelnen Matrizen zu berechnen können die [[Symmetrische Matrix|symmetrischen Matrizen]] $A^TA$ und $AA^T$ verwenden werden.
Es gilt:
$$
\begin{align}
A^TA&=(U\Sigma V^T)^TU\Sigma V^T \\
&=(V^T)^T\Sigma^TU^T U\Sigma V^T \\
&=V\Sigma\Sigma V^T \\
&=V\Sigma^2V^T
\end{align}
$$
Die Spalten von V enthalten als die [[Eigenwerte und Eigenvektoren|Eigenvektoren]] und $\Sigma^2$ die [[Eigenwerte und Eigenvektoren|Eigenwerte]] von $A^TA$ (siehe [[Singulärwertzerlegung]]).
Analog
$$
\begin{align}
AA^T &= U\Sigma V^T(U\Sigma V^T)^T \\
&= U\Sigma V^T((V^T)^T\Sigma^TU^T) \\
&= U\Sigma V^TV\Sigma U^T \\
&= U\Sigma\Sigma U^T \\
&= U\Sigma^2U^T
\end{align}
$$
erhalten wird die Eigenvektoren $U$ und die Eigenwerte $\Sigma^2$ von $AA^T$.
### Beispiel
Für $A = \begin{bmatrix}4&4\\-3&3\end{bmatrix}$ hat man $A^TA=\begin{bmatrix}25&7\\7&25\end{bmatrix}$
Die Eigenvektoren dieser Matrix ergeben die Matrix $V$ und die Wuzel der Eigenwerte ergibt $\Sigma$.
$$
\operatorname{\det}(A^TA-\lambda I)=
\left|\begin{array}
25-  \lambda & 7 \\
7 & 25-\lambda
\end{array}
\right| = (25-\lambda)^2-7^2 = \lambda^2 -50\lambda-576=0
$$
Daraus erhalten wir $\lambda_{1} =32$ und $\lambda_{2} = 18$. Daraus die Singulärwerte $\sigma_{1}=\sqrt{ 32 }$ und $\sigma_2=\sqrt{ 18 }$.

Berechnet man nun die Eigenvektoren von $A^TA$ mithilfe von $\lambda_1$ und $\lambda_2$ erhält man $v_1=\begin{bmatrix}\frac{1}{\sqrt{ 2 }}\\ \frac{1}{\sqrt{ 2 }}\end{bmatrix}$und $v_{2}=\begin{bmatrix}\frac{1}{\sqrt{ 2 }}\\\frac{-1}{\sqrt{ 2 }}\end{bmatrix}$.

Bis jetzt haben wird:
$$
\begin{bmatrix}
4 & 4 \\
-3 & 3
\end{bmatrix} = \begin{bmatrix}
 &  &  \\
 &  & 
\end{bmatrix}\begin{bmatrix}
\sqrt{ 32 } & 0 \\
0 & \sqrt{ 18 }
\end{bmatrix}\begin{bmatrix}
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} \\
\frac{1}{\sqrt{ 2 }}  & -\frac{1}{\sqrt{ 2 }}
\end{bmatrix}
$$
Die Matrix $U$ kann nun analog mit den Eigenvektoren von $AA^T$ berechnet werden.
Oder aber mit:
$$
AV\Sigma^{-1} = U
$$
Falls $\Sigma$ nicht invertierbar ist kann folgendes angewandt werden:
$$
\frac{1}{\sigma_{n}}Av_{n}=u_{n}
$$
Wobei $v_n$ und $u_n$ sich jeweils auf die Spalte mit dem Index $n$ bezieht.







## Anwendungsbereich
- Bildkompression:
	Das Bild ist ein $49 \times 93$ Graustufenbild.
	Die Grauwerte sind die Matrixelemente der $49 \times 83$ Matrix $A$
	Hier werden $k = 5,10,15,20$ und $25$ Singulärwerte berücksichtigt.
	$$
A \approx \sum_{i=i}^{k}\sigma_{i}u_{i}v_{i}^{T}
$$

![[Bildkompression.png]]
- [[Hauptkomonentenanalyse]] (Principal Component Analysis, PCA) welche vor allem in der Datenanalyse verwendet wird (Data science).
- [[Pseudoinverse]], falls $A^{-1}$ nicht existiert.