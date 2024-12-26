>[!Definition]
>Für $n,m,k \in \mathbb{N}$ gilt $\begin{pmatrix}m+n\\k\end{pmatrix} = \sum_{j=0}^{k}\begin{pmatrix}m\\j\end{pmatrix}\begin{pmatrix}n\\k-j\end{pmatrix}$


**Kombinatorisches Beweis**
Auf der LHS hat man die Anzahl der Möglichkeiten $k$ Elemente aus einer Menge mit $m+n$ Elementen auszuwählen ([[Kombinationen]]).

Auf der RHS hat man die Anzahl der Möglichkeiten $j$ Elemente aus $m$-Elementen auswählen **multipliziert** ([[DMATH/Zählen/Produktregel|Produktregel]]) mit der Anzahl an Möglichkeiten $k-j$ Elemente von $n$ Elementen auszuwählen.
