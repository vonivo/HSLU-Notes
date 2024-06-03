Der Selection-Sort (direktes Auswählen) ist ein [[Vergleichsbasierte Sortieralgorithmen|vergleichsbasierter Sortieralgorithmus]] welcher ähnlich funktioniert wie der [[Insertion Sort]]. Arbeitet jedoch [[Sortieralgorithmus#Stabilität|instabil]].

## Prinzip
- Die Daten werden in einen sortierten Teil und einen unsortierten Teil unterteilt.
- Aus dem unsortierten Teil der Daten wird immer der kleinste Schlüssel gesucht und an den sortierten Teil angefügt.
- Das kleinste Datenelement wird immer mit dem ersten Element des unsortierten Teils vertauscht.
- Nach $n-1$ Durchläufen ist fertig.
![[SelectionSort.png]]![[SelectionSort_stages.png]]

## Implementation
```java
public void sort(int[] data) {
	for(int i = 0; i < data.length - 1; i++) {
		int minIndex = i;
		for (int j = i + 1; j < data.length; j++) {
			if (data[j] < data[minIndex]) {
				minIndex = j;
			}
		}
		swap(minIndex, i, data)
	}
}

private void swap(int i, int j, int[] data) {
	int elt = data[i];
	data[i] = data[j];
	data[j] = elt;
}
```

## Analyse
Da zum Ermitteln des kleinsten Schlüssels immer der gesamte unsortierte Teil durchsucht werden muss, erübrigt sich die Differenzierung in Best-, Worst- und Average-Case.

=> [[Komplexität]] von $O(n^{2})$.
