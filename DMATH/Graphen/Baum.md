>[!Definition]
>Ein Baum, Bezeichnung $T_{n}$ für einen Baum mit $n$ [[DMATH/Graphen/Graph|Knoten]] ist ein **zusammenhängender** [[DMATH/Graphen/Graph|Graph]] der keinen Kreis enthält.

![[Pasted image 20250101112308.png]]

>[!Definition]
>Ein **Wurzelbaum** ist ein Baum, in dem ein Knoten als Wurzel fest gewählt wurde. Die Höhe eines Knoten ist dann die Länge des (eindeutig bestimmten) Weges von der Wurzel zu diesem Knoten.

![[Pasted image 20250101112446.png]]
- $a$ ist die **Wurzel**
- $c$ ist der **Vorgänger** oder **Vater** von $h$
- $g$ ist der **Nachfolger** oder **Sohn** von $b$
- $e,f$ und $g$ sind **Brüder**
- Knoten mit Söhnen heissen **innere Knoten**
- Knoten ohne Söhne heissen **Blätter**

>[!Definition]
>Ein Wurzelbaum heisst $m$**-facher Baum** wenn jeder innere Knoten höchstens $m$ Söhne hat. Ein voller $m$-facher Baum hat stets genau $m$ Söhne an jedem inneren Knoten. Ein $2$-facher Baum heisst Binärbaum.

>[!Theorem]
>1. Ein Baum mit $n$ Knoten hat $n-1$ Kanten.
>2. Ein voller $m$-facher Baum mit $i$ inneren Knoten hat $n=m\cdot i+1$ Knoten.
>3. Ein $m$-facher Baum der Höhe $h$ hat höchstens $m^{h}$ Blätter.