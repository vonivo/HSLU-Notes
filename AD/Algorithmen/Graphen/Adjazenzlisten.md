Die Adjazenzliste beschreibt alle Kanten eines [[AD/Algorithmen/Graphen/Graph|Graphen]].

Sei:
- $G = (V,E)$
- $V = \{ a,b,c,\dots \}$

Für jeden der $n$ Knoten vom $G$ gibt es eine Adjazenzliste, welche alle Endkonten enthält zu welchen eine Kante führt.

Die Adjazenzliste kann unterschiedliche Implementiert werden:
- [[Bäume|Baum]]
- [[Liste]]
- Set
- Map

[[AD/Algorithmen/Komplexität|Speicherkomplexität]] von $O(|V|+|E|)$

=> Bei [[AD/Algorithmen/Graphen/Graph#Gerichteter vs. ungerichteter Graph|ungerichteten]] Graphen wird jede Kante doppelt gespeichert.
=> Vorteilhaft bei [[AD/Algorithmen/Graphen/Graph#Dünn|dünn]] besiedelten Graphen.
![[AdjazenzListe.png]]

## Implementation
```java
class Graph {
	private Map<Node, Set<Node>> map;

	public boolean isNodeInGraph(Node node) {
		return this.map.containsKey(node);
	}

	public boolean addNode(node) {
		if (!isNodeInGraph(node)) {
			map.put(node, new HashSet<>());
			return true;
		}
		return false;
	}

	public isEdgeinGraph(Node from, Node to) {
		if (isNodeInGraph(from)) {
			return map.get(from).contains(to);
		}
		return false;
	}

	public boolean addEdge(Node from, Node to) {
		if (isNodeInGraph(from) && isNodeInGraph(to)) {
			if (!isEdgeInGraph(from, to)) {
				this.map.get(from).add(to);
				return true;
			}
		}
		return false;	
	}
}
```
