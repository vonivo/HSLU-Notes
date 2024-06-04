Mergesort ist ein [[Vergleichsbasierte Sortieralgorithmen|vergleichsbasierter Sortieralgorithmus]], welcher [[Sortieralgorithmus#Stabilität|stabil]] arbeitet.

Wie bereits der [[Quicksort]] wendet der Mergesort das Prinzipt "Teile und Hersche" an.

## Prinzip
**Rekursionsbasis**
- Eine zu sortierende Teilfolge von **einem** Datenelement ist sortiert.

**Rekursionsvorschrift*
1. Die zu sortierende Folge von mehreren Elementen wird in zwei Hälften **halbiert**
![[MergeSort_1.png]]
2. Sortiere die Linke und rechte Hälfte ([[Rekursion|rekursive]] Aufrufe).
	- D.h. auf zwei einfachere Sortierprobleme zurückführen.
	- Weil unabhängig, gegebenenfalls sogar parallel sortierbar.
![[MergeSort_2.png]]
3. Füge die beiden sortierten Hälften zu der verlangten sortierten Folge mit dem Reissverschlussverfahren zusammen
	1. Vergleiche die beiden ersten Elemente der Sortierenden Hälfte
	2. Füge das kleinere Element dem Resultat hinzu. (Falls Die Elemente gleich sind, nimm das linke)
	3. Gehe zu 1. solange nicht bei Hälften abgearbeitet sind.
![[MergeSort_3.png]]

![[MergeSort_4.png]]![[MergeSort_stages.png]]

## Analyse
Beim Halbieren resultieren gleich grosse Teilfolgen (+/- 1 Element).
- Es resultiert garantiert ein [[Balancieren von binären Bäumen|balancierter]] [[Binäre Bäume|binärer Baum]] mit $\log_{2}(n)$ [[Baum Niveaus|Niveaus]].
- Pro Niveau braucht es ungefähr $n$ Vergleiche

=> [[AD/Algorithmen/Komplexität|Komplexität]] von $O(n \log n)$.

Mergesort benötigt aber für das Mischen zusätzlichen Speicherplatz und zwar insgesamt Speicher für $2n$ Elemente.

=> Speicherkomplexität vom $O(n)$.


## Implementation
```java
private statich int[] b;
public void sort(int[] data) {
	b = new int[data.length]
	sort(data, 0, data.length - 1);
}

public void sort(int[] data, left, right) {
	int i,j,k,m;
	if (left < right) {
		m = (left + right) / 2;
		mergeSort(a, left, m);
		mergeSort(a, m + 1, right);
	}

	for (i = left; i <= right; i++) {
		b[i] = data[i];
	}

	for (j = m; j < right; j++) {
		b[right + m - j] = data[j + 1];
	}

	i = left; 
	j = right;
	for (k = left; k <= right; k++) {
		if (b[i] <= b[j]) {
			data[k] = b[i];
			i++;
		} else {
			data[k] = b[j];
			j--;
		}
	}
}
```