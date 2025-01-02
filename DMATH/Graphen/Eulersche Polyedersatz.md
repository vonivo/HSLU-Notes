>[!Theorem]
>Sei $G(V,E)$ ein zusammenhängender, [[Planare Graphen|planarer]] [[DMATH/Graphen/Graph|Graph]] mit $|V|$ Knoten und $|E|$ Kanten. Weiterhin sei $|F|$ die Anzahl Flächen, in welche die Ebene durch $G$ unterteilt wird. Dann gilt die sogenannte **Eulersche Formel:**
>$$
>|V|-|E|+|F|=2
>$$

## Beweis
Sei $G$ ein planarer, zusammenhängender Graph mit $|V|$ Knoten, $|E|$ Kanten und $|F|$ Flächen. Weiter sei $B$ ein Spannbaum von $G$ (durchgezogene rote Linie), d.h. ein [[Baum]], welcher alle Knoten von $G$ enthält (auch Gerüst genannt).
![[Pasted image 20250102113610.png]]
$$
\begin{align}
|V| & =4 \\
|E| & =6 \\
|F| & =4
\end{align}
$$
Der Baum $B$ hat $|V|$ Knoten und somit $|V|-1$ Kanten.

Wir zeichnen nun einem dualen Graph $G^{*}$ zu $G$, indem wir in jede Fläche einen Knoten setzen und zwei dieser Knoten verbinden, wenn sie in benachbarten Flächen sind.
![[Pasted image 20250102113851.png]]
$G^{*}$ hat $4$ Knoten, d.h. gleich viele wie die $|F|$ von $G$. Auch $G^{*}$ hat $6$ Kanten wie $G$.

Nun konstruieren wir einen [[Spannbaum]] $B^{*}$ von $G^{*}$. Da $G^{*}$ und somit auch $B^{*}$ $|F|$ Knoten haben, hat $B^{*}$ genau $|F|-1$ Kanten.
![[Pasted image 20250102114056.png]]
Wie viele Kanten haben nun die beiden Bäume $B$ und $B^{*}$ zusammen?
$B$ hat $|V|-1$ Kanten und $B^{*}$ hat $|F|-1$ Kanten. Natürlich ist die Summe gleich der Anzahl der Kanten von $G$, d.h $|E|$
$\implies |E|=|V|+|F|-2$