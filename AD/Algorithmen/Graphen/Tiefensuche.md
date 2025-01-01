>[!info]
>Die Tiefensuche ist ein [[Graphenalgorithmen|Graphenalgorithmus]] für das Traversieren eines [[AD/Algorithmen/Graphen/Graph|Graphen]].

Die Knoten werden vom Startknonten aus sukzessive **so weit wie möglich** besucht, bis es nicht mehr weiter geht. Dann wird einen Schritt zurückgegangen und den zurückliegenden Optionen nachzugehen.

Die Tiefensuche entspricht einer [[Baumtraversierung]] gemäss:
- **Preorder** -> falls Knoten unmittelbar beim Finden verarbeitet werden.
- **Postorder** -> falls Knoten erst **vor einem Back** verarbeitet werden.

Iterativ kann sie mit Hilfen eines [[AD/Datenstrukturen/Stack|Stack]] relativ einfach implementiert werden.
Mit [[Rekursion]] ist die Implementation einfach möglich.

Die [[AD/Algorithmen/Komplexität|Komplexität]] beträgt $O(|V| + |E|)$

## Ablauf
1. Startpunkt Knoten $a$:
![[Tiefensuche_1.png]]
2. Nächster Knoten $b$ besuchen.
![[Tiefensuche_2.png]]
3. Nächster Knoten $c$ besuchen:
![[Tiefensuche_3.png]]
4. Da keine Optionen mehr vorhanen, zurück zu $b$ und von dort $d$ besuchen:
![[Tiefensuche_4.png]]
5. Kein neuer Knoten, zurück zu $b$ und zurück zu $a$. Von dort aus weiter nach $f$

## Implementation
### Iterativ
```java
public void tfs(Graph g, Node start) {
	LinkedList<Node> wait = new LinkedList<>();
	g.setColor(Color.GRAY);
	wait.push(g);

	while (!wait.isEmpty()) {
		Node node wait.getFirst();
		found = false;
		for (Node next : g.getAllAdjaNodes(node)) {
			if (next.getColor().equals(Color.WHITE)) {
				next.setColor(Color.GRAY);
				wait.push(g);
				found = true;
				break;
			}
		}
		if (!found) {
			LOG.info(node);
			node.setColor(Color.BLACK);
			wait.pop();
		}
	}
}
```

### Rekursiv
```java
public void tfs(Graph g, Node start) {
	start.setColor(Color.GRAY);
	for (Node next : g.getAllAdjaNodes(start)) {
		if (next.getColor().equals(Color.WHITE)) {
			tfs(g, next);
		}
	}

	LOG.info(start);
	start.setColor(Color.BLACK);
}
```