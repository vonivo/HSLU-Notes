>[!Definition]
>Ein **Eulerweg** (bzw. **Eulerkreis**) in einem [[DMATH/Graphen/Graph|Graphen]] $G$ ist ein [[Weg und Kreis|Weg]] (bzw. [[Weg und Kreis|Kreis]]), der jede Kante von $G$ genau einaml durchläuft.


![[Pasted image 20250101141245.png]]
Da beim Ablaufen eines Eulerkreises jeder Knoten der betreten wird, wieder verlassen werden muss, ist es notwendig, dass **alle Knoten** eine **geraden [[Knotengrad]]** besitzen. Diese Bedingung ist sogar hinreichend.

>[!Theorem]
>Jeder zusammenhängende Graph mit mindestens zwei Knoten hat genau dann einen Eulerkreis, wenn alle Ecken geraden Grad haben.


## Konstruktion des Eulerkreises
1. Starte an einem beliebigen Knoten $a$ von $G$. (Damit hat $a$ eine ungeraden (Rest)grad).
2. Hänge immer neue Kante an (keine doppelten)
3. Jeder solche Weg muss in $a$ enden, denn jeder Knoten (bis auf $a$!!) hat geraden Grad und kann also wieder verlassen werden.
	- **Möglichkeit: 1** Jede Kante wurde durchlaufen. -> Fertig
	- **Möglichkeit** **2** Nicht alle Kanten wurden durchlaufen. Dann betrachte den Teilgraphen $H$ von $G$, der aus $G$ durch Entfernen aller durchlaufener Kanten und aller Knoten, die nicht auf übriggebliebenen Kanten liegen, entsteht. $H$ hat ausschliesslich gerade Knotengrade und einen Knoten $b$ mit $G$ gemeinsam.
4. Start die obige Wegkonstruktion in $H$ im Punkt $b$ und füge so erhaltene neuen Weg mit dem alten im Punkt $b$ zusammen.

**Beispiel:**
1. Start im Knoten $v_{0}=1$ und hängen einen Kreis an der wieder in $v_{0}$ endet.![[Pasted image 20250101141939.png]]
2. Wir betrachten den Teilgraphen $H$ (schwarz) wir wählen den Knoten $v_{1}=3$ als zweiten Startpunkt und zeichnen einen weiteren Kreis.
![[Pasted image 20250101142105.png]]
3. Wir betrachten den Teilgraphen $H'$ (schwarz) Wir wählen den Knoten $v_{2}=4$ als zweiten Startpunkt und zeichnen einen weiteren Kreis.
![[Pasted image 20250101142219.png]]
4. Jetzt sind alle Kanten begangen. Wir beginnen bei $v_{0}=1$ folgen dem ersten Weg (blau) bis zum Knoten $v_{1}=3$, folgend dem neuen Weg (rot) bis zum Knoten $v_{2}=4$ und beenden den Grünen Kreis bis wir wieder bei $v_{2}$ sind. Von da aus beenden wir den roten Kreis und von da aus den blauen.
