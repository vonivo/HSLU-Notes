Der Quicksort ist ein [[Vergleichsbasierte Sortieralgorithmen|vergleichsbasierter Sortieralgorithmus]] welcher nach dem Prinzip "Teile und Herrsche" arbeitet.
Er unterteilt das anfängliche Sortiert-Problem in einfachere Teilprobleme:
1. Probleme in Teilprobleme unterteilen.
2. Teilproblem lösen.
3. Teillösungen zur Gesamtlösung zusammensetzen.

Durch das Aufteilen in Teilprobleme wird erreicht, dass:
- Eine [[Rekursion|rekursive]] Lösung möglich ist.
- Die Lösung [[Nebenläufigkeit und Parallelität|parallelisiert]] werden kann.
- Der Lösungsaufwand reduziert werden kann.

## Prinzip
**Rekursionsbasis:**
Eine zu sortierende Folge von einem Datenelement ist sortiert.

**Rekursionsvorschrift**
- Ein zu sortierende Folge von **mehreren** Datenelementen wird in **zwei Teilfolgen getrennt**, dass alle Elemente der ersten Teilfolge kleiner und alle Elemente der zweiten Teilfolge grösser sind als das Trennelement.
- Gegebenenfalls werden die Teilfolgen weiter getrennt.
![[Quicksort_1.png]]

Idealerweise liegt das Trennelement von seiner Wertigkeit her **genau in der Mitte der Folge**, sodass sich die Folge in zwei gleich grosse Teilfolgen aufteilt.

Ziel beim Trennen:
- Das Trennelemente steht nach dem Trennen an der endgültigen Position.
- Alle Elemente links vom Trennelement sind kleiner diesem.
- Alle Elemente rechts vom Trennelement sind grösser/gleich diesem.
![[Quicksort_2.png]]
![[Quicksort_satages.png]]
## Trennelement
Nach dem Trennen sollten möglichst zwei gleich grosse Teilfolgen entstehen.
Die Auswahl des Trennelements sollte jedoch möglichst wenig Aufwand bedeuten.
### Letztes Element
Die gängigste Methode ist einfach das letzte Element der Folge als Trennelement zu wählen.
### Median of Three
Der Median of Three ist eine gängige Methode um das Trennelement zu bestimmen, dabei wird das erste, das mittlere und das letzte Element der Teilfolge vergleichen und das Element in der Mitte wird zum Trennelement.

## Implementation
```java
public void quickSort(int[] data) {
	quickSort(data, 0, data.length)
}

private void quickSort(int[] data, int start, int end) {
	int seperator = data[end - 1];

	int up = start;
	int down = end - 1;
	boolean allChecked = false;
	do {
		while(data[up] < separator) {
			i++;
		}
		
		while(data[down] >= separator) {
			j--;
		}
		
		if (up < down) {
			sap(i, j, data)
		} else {
			allChecked = true;
		}
	} while (!allChecked);

	sap(up, separator, data);
	if (start < (up -1))
		quickSort(data, start, up - 1);
	if (up+1 < end)
		quickSort(data, up + 1, end)
}

private void swap(int i, int j, int[] data) {
	int elt = data[i];
	data[i] = data[j];
	data[j] = elt;
}
```

## Optimierung
Bisher wurden die Elemente so vertauscht, dass Links alle Elemente $< T$ und rechts alle Elemente $\geq T$ zu liegen kamen.
Sprich Elemente welche gleich $T$ sind, kamen immer nach rechts.

Bei vielen gleichen Elementen führt das dazu, dass **T viel zu weit links zu liegen kommt** -> die Trennung wird asymmetrisch, was zu mehr rekursiven Aufrufen führt (wird langsamer).

### Gleiche Elemente vertauschen
Wenn nun Elemente welche $== T$ sind auch vertauscht werden, wird die Aufteilung in Teilfolgen symmetrischer und der Algorithmus schneller.![[Quicksort_3.png]]
Es werden zwar mehr Elemente vertauscht, aber weniger rekursive Aufrufe benötigt.

### Gleiche Elemente in die Mitte
Wenn man den Algorithmus so optimiert, dass gleiche Elemente in der Mitte zu liegen kommen, sind diese Elemente bereits am richtigen Platz.
Dadurch werden die noch zu sortierende rechte und linke Teilfolge kürzer was wiederum dazu führt, dass weniger rekursive Aufrufe gemacht werden müssen.
![[Quicksort_4.png]]=> Jedoch kompliziert.

### Sequenzielles sortieren.
Der klassische Quick-Sort teilt die Teilfolgen auf, bis sich nur noch ein Element darin befindet. Die damit verbundenen rekursiven Methodenaufrufe benötigen viel Zeit.
Daher kann man eine Teilfolge die weniger als $M$-Elemente enthält sequenziell mit [[Insertion Sort]] sortieren. Wählt man $M$ richtig, lässt sich ein Performancegewinn von $20\%$ verbuchen. 

Bester Wert für $M = 25$:
![[QuickSort_threshold.png]]

## Analyse
- Quicksort arbeitet [[Sortieralgorithmus#Stabilität|instabil]].
### Laufzeitanalyse
Das Abarbeiten der Teilfolgen lässt sich als [[Binäre Bäume|binärer Baum]] darstellen, wobei jeder innere Knoten einem Methodenaufruf entspricht.
![[QuickSort_analysis.png]]
#### BestCase
Das gewählte Trennelement kommt immer in die Mitte:
- Daraus resultiert eine [[Balancieren von binären Bäumen|balancierter]] [[Binäre Bäume|binärer Baum]] mit $\log_{2}(n)$ [[Baum Niveaus|Niveaus]].
- Pro [[Baum Niveaus|Niveau]] braucht es immer run $n$ Vergleiche.
=> [[AD/Algorithmen/Komplexität|Komplexität]] von $O(n \log n)$.


#### WorstCase
Im Worstcase kommt das Trennelement immer an ein Ende der Teilfolge.
Der [[Binäre Bäume|binäre Baum]] degeneriert dann zu einer [[Liste]] mit $n$ Elementen.
- Pro Element sind etwa $n$ Vergleiche notwendig
![[QuckSort_analysis_2.png]]
=> [[AD/Algorithmen/Komplexität|Komplexität]] von $O(n^{2})$

#### Average Case
Bei zufälliger Permutation ist der Quicksort **im Mittel nicht viel schlechter als im BestCase**.
Es zeigt isch, dass die Anzahl Niveaus durchschnittlich 39% grösser ist als im BestCase und der QuickSort daher nur 1.4 Mal langsamer arbeitet als im Bestcase.

=> [[AD/Algorithmen/Komplexität|Komplexität]] von $O(n \log n)$.
