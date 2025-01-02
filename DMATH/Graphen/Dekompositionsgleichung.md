Mithilfe der Dekompositionsgleichung lässt sich zu jedem schlichten [[DMATH/Graphen/Graph|Graph]] das [[Chromatisches Polynom|chromatische Polynom]] rekursiv bauen.

Dazu brauchen wir folgende Operationen:
1. $G-e$ ist der Graph der durch Wegglassen er Kate $e$ entsteht.
2. $G_{e}$ ist der Graph der durch zusammenziehen der Kante $e$ und weglassen aller parallelen Kanten entsteht.
![[Pasted image 20250102123700.png]]

Wenn wir nun den Mittlere Graphen $G-e$ betrachten, lässt sich dessen Färbung in 2 Klassen unterteilen, die Knoten $a$ und $b$ welche durch $e$ verbunden waren, haben
1. unterschiedliche Farben
2. gleiche Farben

Die Färbungen der ersten Klasse sind auch gültige Färbungen von $G$ die der Zweiten sind auch zulässige [[Färben|Färbungen]] von $G_{e}$.

>[!Theorem]
>Es gilt $P(G-e,x)=P(G,x)+P(G_{e},x)$ oder
>$$
>P(G,x)=P(G-e,x)-P(G_{e},x)
>$$


**Beispiel**
Im Nachfolgenden gilt: 
![[Pasted image 20250102125608.png]]
1. Entfernen von Kanten, bis alles bestimmt werden kann.
![[Pasted image 20250102125706.png]]
$$
\begin{align}
P(G,x) &= (P(T_{4},x)-P(K_{3},x)) - P(T_{3},x) \\
&=(x\cdot (x-1)^{3}-x(x-1)(x-2))-x(x-1)^{2} \\
&=x\cdot (x-1)^{3}-x(x-1)(x-2)-x(x-1)^{2} \\
&=x(x-1)((x-2)^{2}-(x-2)-(x-1)) \\
&=x(x-1)(x^{2}-2x+1-x+2-x+1) \\
&=x(x-1)(x^{2}-4x+4) \\
&=x(x-1)(x-2)^{2}
\end{align}
$$
