Die Adjazenzmatrix beschreibt alle Kanten eines [[Graph|Graphen]].

Sei:
- $G = (V,E)$
- $V = \{ a,b,c,\dots \}$
Ist die $n\times n$ **Adjazenzmatrix $A$** von $G$ gebeben durch:
- $A[i,j] = 1$ bzw. `true`, falls $(i,j) \in E$
- $A[i,j]$ = 0 bzw. `false`, falls $(i,j) \notin E$ 

Falls $G$ [[Graph#Bewerteter Graph|bewertet]] ist:
- $A[i,j] = f(i,j)$, falls $(i,j) \in E$
- $A[i,j] = \infty$, falls $(i,j) \notin E$

## Eigenschaft
- [[AD/Algorithmen/Komplexität|Speicherkomplexität]] -> $O(|V|^{2})$.
- Bei ungerichteten Graphen resultiert ein [[Symmetrische Matrix|symmetrisches]] $A$ -> Hälfte der Matrix kann gespart werden.
- Vorteilhaft bei [[Graph#Dicht|dicht]] besiedelten Graphen

![[AdjazenzMatrix.png]]

## Implementation
```java
class GraphA {
	private int numOfNodes;
	private String[] nodeNames;
	private boolean[] adjaMx;

	public GraphA(String[] nodes, final boolean[][] adjaMatrix) {
		this.numOfNodes = nodes.length;
		this.nodeNames = nodes;
		this.adjaMx = adjaMatrix;
	}

	public isEdge(int i, int j) {
		return this.adjaMx[i,j];
	}
}

String[] nodes = {"a", "b", "c", "d", "e"};
boolean adjaMx = {
	{false, true, true, true, false},
	{true, false, true, false, false},
	{false, false, true, true, false},
	{false, false, false, false, false},
	{false, false, false, false, false}
}
```
