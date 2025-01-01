Wir stellen uns einen Teil des WWW als gerichteten [[DMATH/Graphen/Graph|Graphen]] vor, wobei die Knoten den Seiten entsprechen und die gerichteten Kanten die Links zwischen den Seiten darstellen.

Jedem Knoten soll nun der PageRank (Gewicht), kurz $PR_{i}$ zugeordnet werden.

**Graph**
![[Pasted image 20250101130154.png]]
Der Page Rank eines Knoten $v$ wird nun wie folgt bestimmt:
$$
PR_{v} = \sum_{\{ x,v \} \in E} \frac{1}{deg(x)}PR_{x}
$$

Daraus folgt:
$$
  
$$
Daraus entsteht folgende [[Matrizen|Koeffizientenmatrix]]:
$$
\begin{bmatrix}
0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{1}{3} & 1 & 1 & 0 \\
1 & 0 & 0 & 0 & 0 & 0  \\
0 & 0 & \frac{1}{3} & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{1}{3} & 0 & 0 & 0
\end{bmatrix}
$$
Aus dieser [[Matrizen|Matrix]] wird nun das folgende [[Lineare Gleichungsysteme]] aufgebaut:
$$
\begin{bmatrix}
0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{1}{3} & 1 & 1 & 0 \\
1 & 0 & 0 & 0 & 0 & 0  \\
0 & 0 & \frac{1}{3} & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{1}{3} & 0 & 0 & 0
\end{bmatrix}\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}=\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}
$$
# Erweiterter PageRank
Beim erweiterten PageRank-Algorithmus wird noch ein Dämpfungsfaktor eingebaut, der das Absprungverhalten des Users simuliert.

Die Dämpfung sagt, in wie vielen Fällen der Benutzer nicht durch Verfolgung eines Links weitersurft, sondern direkt zu einer Seite gesprungen wird und das dabei keine Seite bevorzugt wird.

**Beispiel**
Dämpfungsfaktor: $\frac{4}{5}$

Wir nehmen den "einfachen" PagRank Algorithmus und erweitern ihn durch den Dämpfungsfaktor:
$$
\begin{align}
PR_{1} &= {\color{green}\frac{4}{5}}\cdot PR_{2} + {\color{green} \frac{1}{5} \cdot \frac{1}{6}} \\
PR_{2}&={\color{green} \frac{4}{5}}\left(\frac{1}{3}PR_{3}+PR_{4}+PR_{5}\right) + {\color{green} \frac{1}{5} \cdot \frac{1}{6}}\\
PR_{3}&={\color{green} \frac{4}{5}}\cdot PR_{1} + {\color{green} \frac{1}{5} \cdot \frac{1}{6}}\\
PR_{4}&={\color{green} \frac{4}{5}}\cdot\frac{1}{3}PR_{3} + {\color{green} \frac{1}{5} \cdot \frac{1}{6}}\\
PR_{5}&={\color{green} \frac{4}{5}}\cdot0 + {\color{green} \frac{1}{5} \cdot \frac{1}{6}}\\
PR_{6}&={\color{green} \frac{4}{5}}\cdot\frac{1}{6}PR_{3}+ {\color{green} \frac{1}{5} \cdot \frac{1}{6}}
\end{align}
$$

Daraus entsteht folgendes System:
$$
\begin{align}
\begin{bmatrix}
0 & \frac{4}{5} & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{15} & \frac{4}{5} & \frac{4}{5} & 0 \\
\frac{4}{5} & 0 & 0 & 0 & 0 & 0  \\
0 & 0 & \frac{4}{15} & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{15} & 0 & 0 & 0
\end{bmatrix}\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}+\frac{1}{5}\begin{bmatrix}
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6}
\end{bmatrix}&=\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix} \\
\begin{bmatrix}
0 & 4 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 4 & 4 & 0 \\
4 & 0 & 0 & 0 & 0 & 0  \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0
\end{bmatrix}\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}+\begin{bmatrix}
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6}
\end{bmatrix}&=5\cdot\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix} \\
5\cdot\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}-\begin{bmatrix}
0 & 4 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 4 & 4 & 0 \\
4 & 0 & 0 & 0 & 0 & 0  \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0
\end{bmatrix}\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}&=\begin{bmatrix}
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6}
\end{bmatrix} \\
\begin{bmatrix}
5 & 0 & 0 & 0 & 0 & 0 \\
0 & 5 & 0 & 0 & 0 & 0 \\
0 & 0 & 5 & 0 & 0 & 0 \\
0 & 0 & 0 & 5 & 0 & 0 &  \\
0 & 0 & 0 & 0 & 5 & 0 \\
0 & 0 & 0 & 0 & 0 & 5
\end{bmatrix}\cdot\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}-\begin{bmatrix}
0 & 4 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 4 & 4 & 0 \\
4 & 0 & 0 & 0 & 0 & 0  \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0
\end{bmatrix}\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix}&=\begin{bmatrix}
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6}
\end{bmatrix} \\
\left[\begin{bmatrix}
5 & 0 & 0 & 0 & 0 & 0 \\
0 & 5 & 0 & 0 & 0 & 0 \\
0 & 0 & 5 & 0 & 0 & 0 \\
0 & 0 & 0 & 5 & 0 & 0 &  \\
0 & 0 & 0 & 0 & 5 & 0 \\
0 & 0 & 0 & 0 & 0 & 5
\end{bmatrix}-\begin{bmatrix}
0 & 4 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 4 & 4 & 0 \\
4 & 0 & 0 & 0 & 0 & 0  \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \frac{4}{3} & 0 & 0 & 0
\end{bmatrix}\right]\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix} &=\begin{bmatrix}
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6}
\end{bmatrix} \\
\begin{bmatrix}
5 & -4 & 0 & 0 & 0 & 0 \\
0 & 5 & -\frac{4}{3} & -4 & -4 & 0 \\
-4 & 0 & 5 & 0 & 0 & 0 \\
0 & 0 & -\frac{4}{3} & 5 & 0 & 0 \\
0 & 0 & 0 & 0 & 5 & 0 \\
0 & 0 & -\frac{4}{3} &0 & 0 & 5
\end{bmatrix}\begin{bmatrix}
PR_{1} \\
PR_{2} \\
PR_{3} \\
PR_{4} \\
PR_{5} \\
PR_{6}
\end{bmatrix} &=\begin{bmatrix}
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6} \\
\frac{1}{6}
\end{bmatrix}
\end{align}
$$
>[!Definition]
>Gegen seien:
>- ein Netzwerk mit $N$ (im Bsp. $N$=6) Seiten
>- der Dämpfungsfaktor $d$ mit $0\leq d\leq 1$ (im Bsp. $\frac{4}{5}$)
>- Seite $j$ verlinke mit $C_{j}$ verschiedene Seiten (d.h. von Seite $j$ gehen $C_{j}$ Links ab).
>  Dann sind die PageRanks durch folgendes System von $N$ linearen Geleichungen geben:
>  $$
>  PR_{i}=d\cdot \sum_{\text{j hat Link auf i}}\left[\frac{PR_{j}}{C_{j}}\right]+(1-d)\cdot \frac{1}{N}
>  $$



