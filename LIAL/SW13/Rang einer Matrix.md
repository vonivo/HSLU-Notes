Der Rang einer [[Matrizen|Matrix]] ist die Anzahl der linear unabhängigen Zeilen welche nicht null sind.

## Beispiel
$$
A = \begin{pmatrix}
1 & 2 & 3 \\
1 & 2 & 1 \\
3 & 6 & 3
\end{pmatrix}
$$
Damit nun der Rang bestimmt werden kann, müssen alle linear abhängigen Zeilen verschwinden. Dies kann über die [[Gausselimination]] gemacht werden.
Nach der [[Gausselimination]]:
$$
A=\begin{pmatrix}
1 & 2 & 3 \\
0 & 0 & -2 \\
0 & 0 & 0
\end{pmatrix}
$$
Sprich nun kann gezählt werden, wie viele Zeilen nicht null sind.
Dementsprechend:
$$
\operatorname{rang}(A) = 2
$$
