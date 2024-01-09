Ist $A$ eine quadratische $n * n$-[[Matrizen|Matrix]]. $A$ heisst **invertierbar**, **regulär** oder **nichtsingulär**, wenn eine $n * n$-Matrix $B$ existiert, sodass $A * B = B * A = E$. Man nennt $B$ die zu $A$ inverse Matrix und bezeichnet sie mit $B = A^{-1}$.

## Beispiel
$$ A = \begin{pmatrix}
1 & 3 \\
2 & 7
\end{pmatrix}$$
Die Inverse ist:
$$A^{-1} = \begin{pmatrix}
7 & -3 \\
-2 & 1 
\end{pmatrix}
$$
Somit:
$$
\begin{pmatrix}
1 & 3 \\
2 & 7
\end{pmatrix} * 
\begin{pmatrix}
7 & -3 \\
-2 & 1 
\end{pmatrix}
= \begin{pmatrix}
1*7 + 3*-2 & 1*-3 +3-1 \\
2*7 + 7*-2 & 2*-3+7*1
\end{pmatrix} = 
\begin{pmatrix}
7-6 & -3+3 \\
14-14 & -6+7
\end{pmatrix} =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$
# Rechenregeln
Das Inverse eines [[Matrixmultiplikation|Produkts]] $$AB * (AB)^{-1} = (AB)(B^{-1}A^{-1}) =A(BB^{-1})A^{-1} = AIA^{-1}$$
$$ AIA^{-1}= AA^{-1} = I$$


## Invertieren von 2x2-Matrizen
Eine 2x2-Matrix wird invertiert, indem die Zahlen auf der Hauptdiagonale vertauscht werden, das Vorzeichen der restlichen getauscht wird und die Matrix  durch ihre [[Determinante]] geteilt wird:
$$
\begin{pmatrix}
1 & 3 \\
1 & 7
\end{pmatrix}^{-1} = \frac{1}{1\cdot 7 - 1 \cdot 3}
\begin{pmatrix}
7 & -3 \\
-1  & 1
\end{pmatrix}$$

## Inverse von Diagonalen Matrizen
Die Inverse einer [[Diagonalmatrix]] wird gebildet, indem der Kehrwert der Werte genommen wird.
$$
\begin{pmatrix}
a & 0 \\
0 & b
\end{pmatrix}^{-1} =
\begin{pmatrix}
	\frac{1}{a} & 0 \\
 0 & \frac{1}{d}
\end{pmatrix}
$$

