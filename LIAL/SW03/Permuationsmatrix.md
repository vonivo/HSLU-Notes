Eine Permutationsmatrix $P$ ist eine quadratische $n * n$-[[Matrizen|Matrix]], bei der jede Zeile und jede Spalte genau ein Element $1$ enthält, wobei alle anderen Elemente verschwinden (0 sind).  

## Multiplikation
* [[Matrixmultiplikation|Multipliziert]] man eine Matrix $A$ von links mit einer Permutationsmatrix $(PA)$, führt dies zum Vertauschen der Zeilen von A. 

* Entsprechend führt die Multiplikation von rechts $(AP)$ zum Vertauschen der Spalten


Mit anderen Worten: Eine Permutationsmatrix $P$ entsteht aus einer [[Einheitsmatrix]], indem die Zeilen (bzw. Spalten) umgeordnet werden.


## Beispiel
$$
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix} *
\begin{pmatrix}
2 & 3 \\
4 & -5
\end{pmatrix} =
\begin{pmatrix}
4 & -5 \\
2 & 3
\end{pmatrix}
$$
$$
\begin{pmatrix}
2 & 3 \\
4 & -5
\end{pmatrix}*
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix} =
\begin{pmatrix}
3 & 2 \\
-5 & 4
\end{pmatrix}$$

