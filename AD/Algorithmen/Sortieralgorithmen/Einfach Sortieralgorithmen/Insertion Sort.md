Der Insertion-Sort (direktes Einfügen) ist ein [[Vergleichsbasierte Sortieralgorithmen|vergleichsbasierter Sortieralgorithmus]], welcher [[Sortieralgorithmus#Stabilität|stabil]] arbeitet.

## Prinzip
- Beim Insertion-Sort wird zwischen dem sortierten Teil und einem unsortierten unterschieden.
- Der Algorithmus nimmt immer das nächste Element des unsortierten Teils und fügt es an der richtigen Stelle im sortierten Bereich ein.
- Im sortierten Teil werden alle Elemente mit grösserem Schlüssel nach rechts verschoben.
- Nach $n-1$ Einfügen ist das Array sortiert.
![[Insertion_Sort.png]]
![[Insertion_Sort_stages.png]]

## Implementation

```java
public void sort(int[] data) {
	int currentElement;
	int j;
	for (int i = 1; i < data.length; i++) {
		currentElement = data[i];
		j = i;
		while (currentElment < data[j - 1] && j > 0) {
			data[j] = data[j - 1];
			j--;
		}
		data[j] = currentElement;
	}
}
```

### Optimierung
Bei jedem Durchlauf der `while`-Schleife sind immer 2 Vergleiche nötig, was aufwendig ist.
Mit dem Trick, dass `a[0]` neu nur zum Speichern von dem `currentElement` benutzt wird, fällt der Vergleich $j>0$ weg, da `a[j-1] > elt` dann immer terminiert.

#### Implementation
```java
public void sort(int[] data) {
	int currentElement;
	int j;
	for (int i = 1; i < data.length; i++) {
		data[0] = data[i]
		currentElement = data[i];
		j = i;
		while (currentElment < data[j - 1]) {
			data[j] = data[j - 1];
			j--;
		}
		data[j] = currentElement;
	}
}
```

## Analyse
### Bestcase
Der Bestcase für Insertion-Sort ist, wenn die Daten bereits sortiert vorliegt.

Pro Durchlauf ist somit nur $1$ Vergleich nötig (`currentElement < data[j-1]`)

$$
\begin{align}
C_{min} &= \sum_{i=2}^{n}1 \\
&=\sum_{i=1}^{n-1}1 \\
&=n-1
\end{align}
$$
=> [[Komplexität]] von $O(n)$.

## Worstcase
Der Worstcase für Insertion-Sort ist, wenn die Daten umgekehrt sortiert vorliegen.

Pro Durchlauf sind nun $1+(i-1) \implies i$ Vergleiche notwendig:
$$
\begin{align}
C_{max} &= \sum_{i=2}^{n}i \\
&=\frac{n(n+1)}{2} -1 \\
&=\frac{n^{2}}{2}+\frac{n}{2} -1
\end{align}
$$
=> [[Komplexität]] von $O(n^{2})$.

### Averagecase
Im Durchscnitt kommt das Element etwa in die Mitte des sortierten Teils.
Somit sind $1+\frac{i-1}{2}$ Vergleiche notwendig.
$$
\begin{align}
C_{avg} &= \sum_{i=2}^{n}\left(1+\frac{i-1}{2}\right) \\
&= \sum_{i=2}^{n}\frac{i+1}{2} \\
&=\frac{1}{2}\sum_{i=2}^{n}i+1 \\
&=\frac{1}{2}\left(\sum_{i=2}^{n}i + \sum_{i=2}^{2}1\right) \\
&=\frac{1}{2}\left(\sum_{i=2}^{n}i + (n-1)\right) \\
&=\frac{1}{2}\left(\frac{n(n+1)}{2} -1 + (n-1)\right) \\
&=\frac{1}{2} \times \frac{1}{2}(n^{2}+n-2+2n-2) \\
&=\frac{1}{4}(n^{2}+3n-4)
\end{align}
$$
=> [[Komplexität]] von $O(n^{2})$

