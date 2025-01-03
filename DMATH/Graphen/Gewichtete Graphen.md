>[!Definition]
>Ein gewichteter [[DMATH/Graphen/Graph|Graph]] $G=(V,E,w)$ wird durch einen zusammenhängenden Graphen $G$ und eine **Gewichtsfunktion** $w$ beschrieben:
>$$
>w:E\to(0,\infty), \{ u,v \} \mapsto w(u,v)
>$$
>Sie ordnet jeder Kante $e=\{ u,v \}$ ihr Gewicht $w(\{ u,v \})$ zu. Aus lauter Bequemlichkeit schreiben wir dafür einfach $w(u,v)$.

![[Pasted image 20250103091411.png]]


>[!Definition]
>Die **Länge** oder das **Gwicht** eines [[Weg und Kreis|Weges]]
>$$
>u_{0},u_{1},\dots u_{n} \text{ mit } \{ u_{k-1},u_{k} \}\in E, k=1,2,3\dots,n
>$$
>in $G$ ist die Summe der Gwichte sämtlicher Kanten des Wegs:
>$$
>w(u_{0},u_{1},\dots ,u_{n})=w(u_{0},u_{1})+w(u_{1},u_{2})+\dots+w(u_{n-1}, u_{n})
>$$
>Der **Abstand** $d(u,v)$ zwischen zwei Knoten $u,v\in V$ ist das Minimum der Längen aller Wege von $u$ nach $v$.
>
>Ei Weg der Länge $d(u,v)$ von $u$ nach $v$ wird kürzester Weg gennant (es kann mehrere Wege geben).


**Beispiel**
![[Pasted image 20250103092046.png]]
$$
\begin{align}
&u,v &w(u,) &=7 \\
&\color{yellow}u,c,v& \color{yellow}w(u,c,v)&=11 \\
&\color{green}u,c,b,a,v &\color{green}w(u,c,b,a,v) &=13 \\
&\color{\pink}u,b,v &\color{\pink}w(u,b,v)&=4
\end{align}
$$
Somit ist $d=(u,v)=4$
