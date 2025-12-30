Die Bedarfe $b_{i}; i=1,..,m$ (Personal, Betriebsmittel, Finanzen, Produkte) müssen durch die Aktivitäten $a_{j}; j=1,\dots,n$ (Produktion, Transporte, Einkäufe) gedeckt werden.

1. Entscheidungsvariable: $x_{j}$ gibt das Niveau / Intensität der Aktivität $j$, $j=1,\dots,n$ an.
2. Daten
	1. $b_{i}$: Menge des Bedarfs. $i=1,\dots,m$
	2. $a_{i,j}$: Menge des Bedarfs $i$ welche von einer Einheit der Aktivitä $j$ gedeckt wird. $i=1,\dots,m$ und $j=1,\dots,n$
	3. $c_{j}$ Zielbeitrag (Kosten) einer Einheit der Aktivität $j$, $j=1,\dots,n$

## Modell
Minimiere $\sum_{j=1}^{n}c_{j}x_{j}$ unter den Bedingungen:
$$
\begin{align}
\sum_{j=1}^{n}a_{i,j}x_{j} & \geq b_{i} & \text{für alle }i =1,\dots,m \\
x_{j} & \geq 0 & \text{für alle }j=1,\dots,n
\end{align}
$$
**Beispiel**
![[Überdeckungsmodell.png]]