---
aliases:
  - Weg
  - Kreis
---
Der **Weg** $P_{n}$ besitzt die [[DMATH/Graphen/Graph|Knotenmenge]] $\{ 1,2,\dots,n \}$ und die [[DMATH/Graphen/Graph|Kantenmenge]] $\{ \{ 1,2 \},\{ 2,3 \}\dots,\{ n-1,n \} \}$
![[Pasted image 20250101111936.png]]
Ein **Kreis** $C_{n}$ besitzt die Knotenmenge $\{ 1,2,\dots,n \}$ und die Kantenmenge $\{ \{ 1,2 \},\{ 2,3 \},\dots,\{ n-1,n \},\{ n,1 \} \}$
Ein Kreis ist also ein geschlossener Weg.
![[Pasted image 20250101112154.png]]

>[!Definition]
>Ein **Web** in $G=(V,E)$ von Knoten $x_{0}$ zum Knoten $x_{n}$ der Länge $n$ ist eine Folge von $n$ Kanten $e_{1}=\{ x_{0},x_{1} \},e_{2}=\{ x_{1},x_{2} \},\dots,e_{n}=\{ x_{n-1},x_{n} \}$
>Ist der Graph schlicht, genügt es einfach die Folge der Knoten $x_{0},x_{1},\dots,x_{n-1},x_{n}$ anzugeben.
>Ein Weg oder ein Kreis heissen **einfach**, falls jede Kante höchstens einmal vorkommt.

**Beispiel**
Bestimme die Anzahl Wege der Länge $3$ (zwischen zwei beliebigen, nicht notwendigerweise verschiedenen Knoten) im vollständigen Graphen $K_{3}$
$$
\begin{align}
\text{\# Anzhl Wege der Länge 3}&=[A(K_{3})]^{3} \\
&=\begin{bmatrix}
0 & 1 & 1 \\
1 & 0 & 1 \\
1 & 1 & 0
\end{bmatrix}\cdot \begin{bmatrix}
0 & 1 & 1 \\
1 & 0 & 1 \\
1 & 1 & 0
\end{bmatrix}\cdot\begin{bmatrix}
0 & 1 & 1 \\
1 & 0 & 1 \\
1 & 1 & 0
\end{bmatrix} \\
&=\begin{bmatrix}
0 & 1 & 1 \\
1 & 0 & 1 \\
1 & 1 & 0
\end{bmatrix}\cdot\begin{bmatrix}
2 & 1 & 1 \\
1 & 2 & 1 \\
1 & 1 & 2
\end{bmatrix} \\
&=\begin{bmatrix}
2 & 3 & 3 \\
3 & 2 & 3 \\
3 & 3 & 2
\end{bmatrix}
\end{align}
$$
$\implies$ Diese Matrix gibt an, von welchem Knoten $x$ es zum Knoten $y$ wie viele Wege der Länge $3$ gibt.

Bsp gibt es $2$ Wege der Länge $3$ von Knoten $3$ zu Knoten $3$.

>[!Definition]
>Ist $A(G)$ die [[DMATH/Graphen/Matrizen/Adjazenzmatrix|Adjazenzmatrix]] des Graphen $G$, dann ist der $(i,j)$-te Eintrage der Matrix $A(G)^{l}$ ($l=1,2,\dots$) gleich der Anzahl Wege der Länge $l$ in $G$ vom $i$-ten zum $j$-ten Knoten.
