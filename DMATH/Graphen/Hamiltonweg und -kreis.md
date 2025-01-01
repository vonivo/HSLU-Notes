>[!Definition]
>Ein **Hamiltonweg** (bzw. **Hamiltonkreis**) in einem [[DMATH/Graphen/Graph|Graph]] $G$ ist ein einfacher [[Weg und Kreis|Weg]] (bzw. [[Weg und Kreis|Kreis]]), der jeden Knoten von $G$ genau einmal durchläuft.

**Beispiel**
![[Pasted image 20250101142532.png]]
Die Frage ob ein Graph ein Hamiltonkreis enthält ist ein $NP$-vollständiges Problem. (Traveling Salesman Problem)

>[!Theorem]
>Ein Graph mit $n\geq 3$ Knoten und $deg(v)\geq \frac{2}{n}$ für alle Knoten $v$ hat einen Hamiltonkreis.

>[!Theorem]
>Gilt in $G$ mit $n\geq 3$ auch $deg(u)+deg(v)\geq n$ für jedes Paar $u,v$ von nichtbenachbarten Knoten, so hat $G$ einen Hamiltonkreis.



