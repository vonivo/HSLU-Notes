Der Algorithmus von S. Warshall ist ein [[Graphenalgorithmen|Graphenalgorithmus]] welcher alle möglichen Pfade findet.

Die transitive Hülle $G^{*}$ eines [[Graph]] $G$ gibt an, zwischen wlechen Knoten einen direkten oder indirekten Pfad existiert. Damit wird die [[Adjazenzmatrix]] erweitert.

$G^{*}$ besitzt daher zusätzlich jeweils eine Kanten $(x,y)$ wenn $y$ von Knoten $x$ aus erreichbar ist.
![[TransitiveHülle.png]]

## Prinzip
Mit einer Kante $(x,y)$ und einer Kante $(y,z)$ folgt auch eine Kante $(x,z)$.
=> Der Knoten $z$ ist von Knoten $x$ aus erreichbar.
![[Warshall_1.png]]
Jeder Knoten kann potenziell ein Zwischenknoten sein.

Es spielt keine Rolle, in welcher Reihenfolge die Zwischenknoten eingezogen werden:
![[Warshall_2.png]]

Damit kann schon die transitive Hülle ermittelt werden:
```java
// pseudo
for knoten : V
	for eingehend : eingehendeKanten(knoten)
		for ausgehend: ausgehendeKanten(knoten)
			füge(i, j) zu E hinzu.
```

## Implementation
Mit einer [[Adjazenzmatrix]] lässt sich der Algorithmus einfach implementieren.
```java
public boolean transitiveClosure() {
	boolean[][] transClosure = new boolean[numNodes][numNodes];
	for (int i = 0; i < numNodes; i++) {
		transClosure[i] = Arrays.copyOf(adjaMx[n], numNodes);
	}

	for (int node = 0; node < numNodes; node++) {
		for (int i = 0; i < numNodes; i++) {
			if (transClosure[i][node]) {
				for (int j = 0; j < numOfNodes; j++) {
					if (transClosure[node][j]) {
						transClosure[i][j] = true;
					}
				}
			}
		}
	}	
	return transClosure;
}
```