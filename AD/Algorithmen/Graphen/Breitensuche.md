>[!info]
>Die Breitensuche ist ein [[Graphenalgorithmen|Graphenalgorithmus]] für das Traversieren eines [[AD/Algorithmen/Graphen/Graph|Graphen]].

Bei der Breitensuche werden vom Startknoten aus in der Reihenfolge mit kürzester zunehmender Pfadlänge (Anzahl Kanten) besucht:
- Nachdem alle Knoten mit der Pfadlänge $d$ verarbeitet wurden, werden jene mit $d + 1$ angegangen
- Die Suche terminiert, wenn bei der Pfadlänge $d$ keine neuen Knoten gefunden wurden.

Die Breitensuche entspricht einer [[Baumtraversierung]] gemäss **Ebenen-Ordnung**.

Implementiert wird die Breitensuche iterativ mithilfe einer **FIFO-[[Queue]]**.
Mit [[Rekursion]] ist die Implementation nicht so intuitiv.

=> [[AD/Algorithmen/Komplexität|Komplexität]] vom $O(|V| + |E|)$.

## Beispiel
Start $a$:
![[Breitensuche_1.png]]

1. Besuche alle Knoten von A mit einer Pfadlänge $1$:
![[Breitensuche_2.png]]
2. Nächste Knoten von $b, c, f$ aus suchen:
![[Breitensuche_3.png]]
3. Nächste Knoten von $d$ aus suchen:
![[Breitensuche_4.png]]


## Implementation
```java
public void bfs(Graph g, Node start) {
	Queue<Node> wait = new LinkedList<>();
	start.setColor(Color.GRAY);
	wait.add(start);

	while (!wait.isEmpty()) {
		Node node = wait.remove();
		LOG.info(node);            // verarbeiten
		node.setColor(Color.BLACK);
		for (Node next : g.getAllAdjaNodes(node)) {
			if (next.getColor().equals(Color.WHITE)) {
				next.setColor(Color.GRAY);
				wait.add(next)
			}
		}
	}
}
```

