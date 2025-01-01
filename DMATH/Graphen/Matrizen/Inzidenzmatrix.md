Die **Inzidenzmatrix** $B(G)$ ist die $n\times m$-[[Matrizen|Matrix]] eines [[DMATH/Graphen/Graph|Graph]] mit den Komponenten:
$$
B_{ij}:=\begin{cases}
1&\text{falls Knoten i auf Kante j liegt} \\
0 & \text{sonst} \\
2 & \text{wenn ein Loop}
\end{cases}
$$

dabei ist $n$ die Anzahl Knoten und $m$ die Anzahl Kanten.
**Beispiel**
![[Pasted image 20250101134310.png]]
$$
B(G)= \begin{array}{c|ccccccc}
 & 1 & 2 & 3 & 4 & 5 & 6 & 7 \\
\hline1 & 1 & 0 & 1 & 1 & 0 & 0 & 0 \\
2 & 1 & 1 & 0 & 0 & 0 & 0 & 0 \\
3 & 0 & 1 & 1 & 0 & 1 & 1 & 0 \\
4 & 0 & 0 & 0 & 1 & 1 & 0 & 1 \\
5 & 0 & 0 & 0 & 0 & 0 & 1 & 1
\end{array}
$$

