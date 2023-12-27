Falls die [[Matrizen|Matrix]] quadriert wird, bleiben die [[Eigenwerte und Eigenvektoren|Eigenvektoren]] gleich, die [[Eigenwerte und Eigenvektoren|Eigenwerte]] werde allerdings quadriert. Für jeden Eigenvektor $x$ zum Eigenwert $\lambda$ gilt:
$$
A^2x = AAx=\lambda Ax= \lambda\lambda x=\lambda^2x
$$
und somit ist x auch ein Eigenvektor von $A^2$ zum Eigenwert $\lambda^2$.

Um eine effizient die $n$-te Potenz einer Matrix $A$ zu berechnen, wird dies über die [[Diagonalisieren von quadratischen Matrizen|Diagonalisierung]] gemacht.

$$
A^k=V\Lambda^kV^{-1}
$$

## Herleitung am Beispiel $A^3$
$$
\begin{align}
A &= V\Lambda V^{-1} \\
A^3 &= V\Lambda V^{-1}V\Lambda V^{-1}V\Lambda V^{-1} \\
&= V\Lambda\Lambda V^{-1}V\Lambda V^{-1} \\
&= V\Lambda\Lambda\Lambda V^{-1} \\
&= V\Lambda^3V^{-1}
\end{align}
$$
