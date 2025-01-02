>[!Definition]
>Ein **Spannbaum** oder **Gerüst** eines Graphen $G=(V,E)$ ist ein zusammenhängender kreisfreier Untergraph (Baum), der all Knoten aus $V$ enthält.

## Anzahl der Spannbäume bestimmen
Um die Anzahl der Spannbäume zu bestimmen, wird ähnlich zu der [[Dekompositionsgleichung]] ein rekursiver Algorithmus verwendet.

Hier müssen wird wiederum zwei Operationen einführen:
1. $G-e$ der Graph, der aus $G$ durch Weglassen der Kante $e$ entsteht
2. $G\text{\\}e$ der Graph, der aus $G$ durch Zusammenziehen der Kante $e$ und Weglassen aller Schlingen entsteht. **Parallele Kanten werden nicht weggelassen.**
![[Pasted image 20250102143646.png]]

Nun können wir wiederum in zwei Teilklassen unterscheiden:
1. Gerüste von $G$, die $e$ enthalten. Diese Gerüste gehen durch Zusammenziehen der Kante $e$ in ein Gerüst des Graphen $G\text{\\}e$ über und auch jedem Gerüst von $G\text{\\}e$ entspricht genau ein Gerüst von $G$ (das $e$ enthält)
2. Gerüste von $G$, die $e$ **nicht** enthalten. Ein Gerüst dieser Klasse ist auch ein Gerüst des Graphen $G-e$ und umgekehrt.
>[!Theorem]
>Für die Anzahl Gerüste $t(G)$ des Graphen $G$ gilt:
>$$
>t(G) = t(G-e)+t(G/e)
>$$

>[!Theorem]
>- Die Anzahl der Gerüste eines Baumes $t(T_{n}) =1$
>- Die Anzahl der Gerüste eines Kreises $t(C_{n}) =n$


Nun löst man einen Graphen so auf, bis man nur noch Bäume oder Kreise hat:
![[Pasted image 20250102150624.png]]
