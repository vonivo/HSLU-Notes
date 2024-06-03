Buble-Sort ist ein [[Vergleichsbasierte Sortieralgorithmen|vergleichsbasierter Sortieralgorithmus]] welcher [[Sortieralgorithmus#Stabilität|stabil]] arbeitet.

## Prinzip
- Die Daten werden in einen sortierten und einen unsortierten Teil unterteilt.
- Zwei benachbarte Elemente werden vertauscht, falls ihre Schlüssel nicht aufsteigend geordnet sind.
- Damit wächst der final sortierte Teil sukzessive und der unsortierte reduziert sich dagegen laufend.
- Nach $n-1$ durchläufen sind die Daten sortiert.
![[BubbleSort.png]]![[BubbleSort_stages.png]]

## Implementation
```java
public void sort(int data[]) {
	for (int i = 0; i < data.length - 1; i++) {
		for (int j = 0; i < data.length - 1 - i; j++) {
			if (data[j] > data[j + i]) {
				int elt = data[j];
				data[j] = data[j + 1];
				data[j + 1] = elt;
			}
		}
	}
}
```

## Analyse
Der Algorithmus arbeitet mit einer [[AD/Algorithmen/Komplexität]] von $O(n^{2})$, lässt sich aber so modifizieren, dass er im Bestcase mit $O(n)$ durchläuft. Sobald keine Elemente mehr vertauscht werden, sind die Daten sortiert.