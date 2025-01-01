>[!Definition]
>Der **Grad** $deg(v)$ eines [[DMATH/Graphen/Graph|Knotens]] $v\in V$ ist gleich der Anzahl [[DMATH/Graphen/Graph|Kanten]] vom $G$, die $v$ enthalten. Schlingen werden dadurch doppelt gezählt.
>$$
>\begin{align}
deg(v) &= 0 \to v \text{ heisst isolierte Ecke} \\
deg(v) &= 1 \to v \text{ heisst Endecke}
\end{align}
>$$

Addiert man alle Grade aller Knoten, zählt man jede Kante doppelt. Daher gilt:
>[!Theorem]
>$$
>\sum_{v\in V}deg(v)=2\cdot |E|
>$$

