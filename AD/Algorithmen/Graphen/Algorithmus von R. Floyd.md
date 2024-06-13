>[!info]
>Der [[Graphenalgorithmen|Graphenalgorithmus]] von R. Floyd berechnet die kürzeste Distanz zweier Konten eines [[Graph|Graphen]].


Um die kürzeste Entfernung zwischen zwei Knoten zu finden, kann der [[Algorithmus von S. Warshall]] geringfügig angepasst werden.
Daraus resultierte ein **all Pair Shortest Path Problem**.
Anstelle der booleschen [[Adjazenzmatrix]] verwendet man die bewertete Adjazenzmatrix.
![[Floyd_1.png]]
Für jeden Pfad, welcher zwischen zwei Knoten neu ausgemacht wird, überschreibt den bisherigen Pfad.
Nun muss angepasst werden, dass der bestehende nur angepasst wird, wenn der aktuelle kleiner ist.

=> Die [[AD/Algorithmen/Komplexität|Komplexität]] beträgt $O(n^{3})$, wobei $n = |V|$.

## Implementation
```java
public boolean transitiveClosure() {
	boolean[][] transClosure = new boolean[numNodes][numNodes];
	for (int i = 0; i < numNodes; i++) {
		transClosure[i] = Arrays.copyOf(adjaMx[n], numNodes);
	}

	for (int node = 0; node < numNodes; node++) {
		for (int i = 0; i < numNodes; i++) {
			if (transClosure[i][node] < Integer.MAX_VALUE) {
				for (int j = 0; j < numOfNodes; j++) {
					if (transClosure[node][j] < Integer.MAX_VALUE) {
							int newLength = transClosure[node][j] + transClosure[i][node]
						if (transClosure[i][j] > newLength) {
							transClosure[i][j] = newLength;
						}
						
					}
				}
			}
		}
	}	
	return transClosure;
}
```
