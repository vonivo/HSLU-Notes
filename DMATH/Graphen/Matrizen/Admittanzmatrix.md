Die Differenz der [[Gradmatrix]] $D(G)$ und der [[DMATH/Graphen/Matrizen/Adjazenzmatrix|Adjazenzmatrix]] $A(G)$ eines [[DMATH/Graphen/Graph|Graphen]] $G$
$$
L(G)=D(G)-A(G)
$$
Heisst **Admittanzmatrix** (oder **Laplace**-**Matrix**). 

Für Knoten $v\in V=\{ 1,2,\dots,n \}$ des Graphen $G$ bezeichnet $L_{v}(G)$ die Matrix, die durch Streichen der $v$. Zeile und $v$. Spalte aus $L(G)$ hervorgeht.

>[!Theorem]
>Es sei $G=(V,E)$ ein Graph und $v\in V$ ein beliebiger Knoten und $L(G)$ die Admittanzmatrix dieses Graphen. Dann ist die Anzahl der Gerüste dieses Graphen durch $t(G)=\det(L_{v}(G))$(siehe [[Determinante]]) bestimmt.

**Beispiel**
![[Pasted image 20250103103420.png]]
$$
\begin{align}
A(G)&=\begin{bmatrix}
0 & 1 & 1 & 0 \\
1 & 0 & 1 & 1 \\
1 & 1 & 0 & 1 \\
0 & 1 & 1 & 0
\end{bmatrix} \\
D(G) & =\begin{bmatrix}
2 & 0 & 0 & 0 \\
0 & 3 & 0 & 0 \\
0 & 0 & 3 & 0 \\
0 & 0 & 0 & 2
\end{bmatrix} \\
\end{align}
$$
$$
\begin{align}
L(G)&=D(G)-A(G) \\
&=\begin{bmatrix}
2 & 0 & 0 & 0 \\
0 & 3 & 0 & 0 \\
0 & 0 & 3 & 0 \\
0 & 0 & 0 & 2
\end{bmatrix}-\begin{bmatrix}
0 & 1 & 1 & 0 \\
1 & 0 & 1 & 1 \\
1 & 1 & 0 & 1 \\
0 & 1 & 1 & 0
\end{bmatrix} \\
&=\begin{bmatrix}
2 & -1 & -1 & 0 \\
-1 & 3 & -1 & -1 \\
-1 & -1 & 3 & -1 \\
0 & -1 & -1 & 2
\end{bmatrix}
\end{align}
$$
$$
L_{1} = \begin{bmatrix}
3 & -1 & -1 \\
-1 & 3 & -1 \\
-1 & -1 & 2
\end{bmatrix}
$$
$$
\begin{align}
t(G) &= \det(L_{1}(G)) \\
&= \begin{array}{|ccc|cc}
3 & -1 & -1 & 3 & -1 \\
-1 & 3 & -1 & -1 & 3 \\
-1 & -1 & 2 & -1 & -1
\end{array} \\
&=(3*3*2+(-1)*(-1)*(-1)+(-1)*(-1)*(-1))-((-1)*3*(-1)+(-1)*(-1)*3+2*(-1)*(-1)) \\
&=16-8 \\
&=8
\end{align}
$$


