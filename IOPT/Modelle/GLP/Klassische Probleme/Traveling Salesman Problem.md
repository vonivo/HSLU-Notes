Gegeben:
- Menge $V$ von $n$ Städten
- Für alle (geordneten) Paare von Städten $(i,j)\in VxV$ Reisedistanz $d_{i,j}$ von Stadt $i$ zu Stadt $j$.

**Problem**
Finde eine Tour, welche alle Städte besucht, minimaler gesamter Länge.

## Lösung
Meistens Problem in Graph formuliert.
- Stadt → Knoten
- Verbindung von einer Stadt zu einer anderen Stadt → Bogen
- Graphen $G=(V,A)$ mit Gewicht $d_{i,j}$ für jeden Bogen $a\in A$

**Erste Formulierung**
1. Für jeden Bogen$(i,j)\in A$, eine binäre Variable $x_{i,j}$: 1, falls $j$ direkt nach $i$ in der Tour besucht wird und 0 sonst.

=> Idee wir gehen in Jeden Knoten genau 1 mal rein und einmal raus.
$$
\begin{align}
\text{min} & \sum_{(i,j)\in A}c_{i,j}x_{i,j} \\
\text{u.d.B:} \\
 & \sum_{j\in V \backslash \{ i \}} x_{i,j} = 1  & \text{for all }i \in V \\
 & \sum_{j\in V \backslash \{ i \}} x_{j,i} = 1  & \text{for all }i \in V \\
 & x_{i,j}\in \{ 0,1 \}  & \text{für alle}(i,j)\in A
\end{align}
$$
**Resultat**
![[Pasted image 20260101165018.png]]
**Zweite Lösung**
=> Verbieten von vor und wieder zurück:
$$
\begin{align}
\text{min} & \sum_{(i,j)\in A}c_{i,j}x_{i,j} \\
\text{u.d.B:} \\
 & \sum_{j\in V \backslash \{ i \}} x_{i,j} = 1  & \text{for all }i \in V \\
 & \sum_{j\in V \backslash \{ i \}} x_{j,i} = 1  & \text{for all }i \in V  \\
 & x_{i,j}+x_{j,i}\leq 1  & \text{ für alle unterschiedlichen}i,j \in V\\
 & x_{i,j}\in \{ 0,1 \}  & \text{für alle}(i,j)\in A
\end{align}
$$
![[TSP2.png]]
**Dritte Lösung**
Füge Subtour-Eliminationsbedingungen hinzu (zwei Versionen):
1. (‘aus jeder Untermenge $S$ raus’)
   $\sum_{i\in S}\sum_{j \notin S}x_{ij}\geq 1$ für alle nicht leeren $S\subset V$
2. (‘nie in einer Untermenge S bleiben’)
	$\sum_{i\in S}\sum_{j\in S\backslash \{ i \}}x_{ij}\leq \mid S\mid-1$ für alle $S\subset V$ mit $2\leq\mid S\mid$

**Formulierung nicht kompakt**: Anzahl Bedingungen wächst enorm schnell (Grössenordnung 2n)


**Vierte Lösung mit Permutation**
- Sei ein gegebener Knoten $\sigma\in V$ der Start der Tour
- Die Tour wird wie folgt beschrieben: $T=(T(0)=\sigma,T(1),T(2),\dots,T(n-1))$ wobei $T(i)\in V$ für alle $i$ und jeder Knoten kommt genau einmal in $T$ vor. Dies entspricht seiner Position in der Tour.

1. Für jeden Knoten $i\in V$ eine Variable $u_{i}$ mit der Position von $i$ in der Tour. ($0\leq i\leq n-1$) für alle $i\in V$
2. Subtouren-Eliminierung. Für alle $(i,j)\in A$ mit $j\neq \sigma$
	$u_{j}-u_{i}\geq 1-n(1-x_{i,j})$
	- Falls $x_{i,j}=0$ dann besagt $u_{j}-u_{i}\geq 1-n(1-x_{i,j}) \Leftrightarrow u_{i}-u_{j}\leq n-1$ das $j$ max. 1-n Position vor $i$ in der Tour ist. (In jedem Fall wahr.)
	- Falls $x_{i,j}=1$, dann besagt $u_{i}-u_{j}\geq 1$ dass $j$ nach $i$ in der Tour ist.

$$
\begin{align}
\text{min} & \sum_{(i,j)\in A}c_{i,j}x_{i,j} \\
\text{u.d.B:} \\
 & \sum_{j\in V \backslash \{ i \}} x_{i,j} = 1  & \text{for all }i \in V \\
 & \sum_{j\in V \backslash \{ i \}} x_{j,i} = 1  & \text{for all }i \in V \\ 
 & u_{j}-u_{i}\geq 1-n(1-x_{i,j}) & \text{für alle }(i,j)\in A \text{ mit } j \neq \sigma \\
 & 0\leq u_{i\leq n-1} & \text{für alle }i \in V\\
 & x_{i,j}\in \{ 0,1 \}  & \text{für alle}(i,j)\in A
\end{align}
$$
