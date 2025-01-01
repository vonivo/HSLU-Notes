Ein [[DMATH/Graphen/Graph|Graph]] kann mittels [[Matrizen]] dargestellt werden, dabei sind vor allem die :
- [[DMATH/Graphen/Matrizen/Adjazenzmatrix|Adjazenzmatrix]]
- [[Inzidenzmatrix]]
- [[Gradmatrix]]
wichtig.

Die [[DMATH/Graphen/Matrizen/Adjazenzmatrix|Adjazenzmatrix]] und die [[Inzidenzmatrix]] halten alle Informationen, so dass ein Graph vollständig beschrieben ist.

>[!Theorem]
>Wenn ein Graph durch die Adjaznzenmatrix $A$, die Inzidenzmatrix $B$ und die Gradmatrix $D$ beschrieben wird, gilt:
>$$
>BB^{T}=A+D
>$$


**Beispiel**
![[Pasted image 20250101135306.png]]
$$
\begin{align}
A(G)&=\begin{bmatrix}
0 & 3 & 2 & 0 \\
3 & 0 & 1 & 1 \\
2 & 1 & 0 & 2 \\
0 & 1 & 2 & 2
\end{bmatrix} \\
B(0)&=\begin{bmatrix}
1 & 1 & 0 & 0 & 0 & 0 & 1 & 1 & 1 & 0 \\
0 & 0 & 1 & 1 & 0 & 0 & 1 & 1 & 1 & 0 \\
1 & 1 & 1 & 0 & 1 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 1 & 1 & 0 & 0 & 0 & 2
\end{bmatrix} \\
D(G)&=\begin{bmatrix}
5 & 0 & 0 & 0 & 0 \\
0 & 5 & 0 & 0 & 0 \\
0 & 0 & 5 & 0 & 0 \\
0 & 0 & 0 & 5 & 0 \\
0 & 0 & 0 & 0 & 5
\end{bmatrix}
\end{align}
$$
$$
\begin{align}
BB^{T} &= A+D \\
\begin{bmatrix}
1 & 1 & 0 & 0 & 0 & 0 & 1 & 1 & 1 & 0 \\
0 & 0 & 1 & 1 & 0 & 0 & 1 & 1 & 1 & 0 \\
1 & 1 & 1 & 0 & 1 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 1 & 1 & 0 & 0 & 0 & 2
\end{bmatrix}\begin{bmatrix}
1 & 0 & 1 & 0 \\
1 & 0 & 1 & 0 \\
0 & 1 & 1 & 0 \\
0 & 1 & 0 & 1 \\
0 & 0 & 1 & 1 \\
0 & 0 & 1 & 1 \\
1 & 1 & 0 & 0 \\
1 & 1 & 0 & 0 \\
1 & 1 & 0 & 0 \\
1 & 1 & 0 & 0 \\
0 & 0 & 0 & 2
\end{bmatrix}&=\begin{bmatrix}
5 & 0 & 0 & 0  \\
0 & 5 & 0 & 0  \\
0 & 0 & 5 & 0  \\
0 & 0 & 0 & 5  \\
\end{bmatrix}+\begin{bmatrix}
0 & 3 & 2 & 0 \\
3 & 0 & 1 & 1 \\
2 & 1 & 0 & 2 \\
0 & 1 & 2 & 2
\end{bmatrix} \\
\begin{bmatrix}
5 & 3 & 3 & 0 \\
3 & 5 & 1 & 1 \\
2 & 1 & 5 & 2 \\
0 & 1 & 2 & 7
\end{bmatrix}&=\begin{bmatrix}
5 & 3 & 3 & 0 \\
3 & 5 & 1 & 1 \\
2 & 1 & 5 & 2 \\
0 & 1 & 2 & 7
\end{bmatrix}
\end{align}
$$
![[Pasted image 20250101140142.png]]