Hier wird die Spektralzerlegung einer [[Symmetrische Matrix|symmetrischen Matrix]] behandelt.
$$
A = \begin{pmatrix}
1 & 3 \\
3 & 1
\end{pmatrix} \text{ hat die EW } \lambda_{1} = 4, \lambda_{2} = -2\text{ und die EV } x_{1} =\frac{1}{\sqrt{ 2 }}\begin{pmatrix}
1 \\
1
\end{pmatrix}, x_{2} = \frac{1}{\sqrt{ 2 }}\begin{pmatrix}
1 \\
-1
\end{pmatrix}
$$
Es gilt also $Ax_{1} = \lambda_{1}x_{1}$ und $Ax_{2} = \lambda_{2}x_{2}$.
$$
\begin{pmatrix}
1 & 3 \\
3 & 1
\end{pmatrix}\begin{pmatrix}
\frac{1}{\sqrt{ 2 }} \\
\frac{1}{\sqrt{ 2 }}
\end{pmatrix} = 4 \begin{pmatrix}
1 & 3 \\
3 & 1
\end{pmatrix}\begin{pmatrix}
\frac{1}{\sqrt{ 2 }} \\
\frac{1}{\sqrt{ 2 }}
\end{pmatrix} \space\space\space\space\space\space\space\space\space\space\space\space\space\space\space\space
\begin{pmatrix}
1 & 3 \\
3 & 1
\end{pmatrix}\begin{pmatrix}
\frac{1}{\sqrt{ 2 }} \\
\frac{-1}{\sqrt{ 2 }}
\end{pmatrix} = -2 \begin{pmatrix}
1 & 3 \\
3 & 1
\end{pmatrix}\begin{pmatrix}
\frac{1}{\sqrt{ 2 }} \\
\frac{-1}{\sqrt{ 2 }}
\end{pmatrix}
$$

Wir fassen die [[Eigenwerte und Eigenvektoren|Eigenvektoren]] Eigenvektoren (hier $x_1$ und $x_2$) als Spalten der Matrix V auf.
$$
V = \begin{pmatrix}
x_{1}  & x_{2}
\end{pmatrix} = \begin{pmatrix}
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} \\
\frac{1}{\sqrt{ 2 }} & \frac{-1}{\sqrt{ 2 }}
\end{pmatrix}
$$
Ebenso fassen wird die [[Eigenwerte und Eigenvektoren| Eingewerte]] (hier $\lambda_1$ und $\lambda_2$) als [[Diagonalmatrix]] $\Lambda$ auf.
$$
\Lambda=\begin{pmatrix}
\lambda_{1}  & 0 \\
0 & \lambda_{2}
\end{pmatrix} = \begin{pmatrix}
4 & 0 \\
0 & -2
\end{pmatrix}
$$

>[!warning] Beachte
>Die Reihenfolge der Spalten sowohl in $V$ wie auch $\Lambda$ ist wichtig.

Nun gilt:
$$
AV = V\Lambda
$$
Da $V$ [[Orthogonale Matrix|orthogonal]] ist gilt $V^{-1} = V^T$
$$
\begin{align}
AV &= V\Lambda \\
AVV^{-1} &= V\Lambda V^{-1} \\
A &= V\Lambda V^{-1} \\
A &= V\Lambda V^{T}
\end{align}
$$
Dabei ist 
- $\Lambda = \operatorname{diag}(\lambda_{1}, \lambda_{2})$ eine [[Diagonalmatrix]] welche die [[Eigenwerte und Eigenvektoren|Eingwerte]] enthält
- $V = (x_{1}, x_{2})$ eine Matrix welche als Spalten der Reihe nach die [[Eigenwerte und Eigenvektoren|Eigenvektoren]] enhält.

$$
\begin{pmatrix}
1 & 3 \\
3 & 1
\end{pmatrix} = \begin{pmatrix}
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} \\
\frac{1}{\sqrt{ 2 }} & -\frac{1}{\sqrt{ 2 }}
\end{pmatrix}\begin{pmatrix}
4 & 0 \\
0 & -2
\end{pmatrix}\begin{pmatrix}
{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} \\
\frac{1}{\sqrt{ 2 }} & -\frac{1}{\sqrt{ 2 }}
\end{pmatrix}
$$
# Spektralzerlegung
Man nennt:
$$
A = \lambda_{1}x_{1}x_{1}^T + \lambda_{2}x_{2}x_{2}^T
$$Die Spektralzerlegung der [[Symmetrische Matrix|symmetrischen Matrix]] $A$.
Allgemein:
$$
A = V\Lambda V^T = \lambda_{1}x_{1}x_{1}^T + \lambda_{2}x_{2}x_{2}^T + \dots+\lambda_{n}x_{n}x_{n}^{T}
$$


