>[!info]
>Der [[Graphenalgorithmen|Graphenalgorithmus]] von Dijkstra berechnet die kürzeste Distanz zweier Konten eines [[Graph|Graphen]].

Der Algorithmus von Dijkstra berechnet die kürzeste Entfernung von **einem Knoten** zu allen anderen -> **Singel Source Shortes Path Problem**.

Ist man nur an einer Distanz zu einem spezifischen Knoten interessiert, kann man den Algorithmus abbrechen sobal dieser gefunden wurde.

Ein Nebenprodukt diese Algroithmus ist ein [[Graph#Spanning Tree|Spanning Tree]].

## Prinzip
Geben:
- $G = (V,E)$
- Startknoten $s \in V$
- allenfalls Zielknoten $z \in V$
- Gewichtungsfuntkion $f(E)$

Gewichtungsfunktion:
- für jede Kante $(i,j) \in E$ -> Gewicht $f(i,j) \geq 0$
- falls $(i,j) \notin E$ -> Geweicht $f(i,j) = \infty$
- keine trivialen Zyklen -> Gewicht $f(i,j) = 0$

Voraussetzungen:
- Gewichte sind positiv.

- Eine Knotenmenge $T \subseteq V$ beschreibt den bereits bearbeiteten [[Graph#Teilgraph|Teilgraphen]] von $G$.
- $T$ wird schrittweise um einen Knoten erweitert, sodass für alle $k \in T$ gilt: Der Weg mit der kürzesten Entfernung von $s$ nach $k$ verläuft ausschliesslich über Knoten von $T$
- $NK = \{ nk | \text{nk is mindestens einem  }k \in T \text{ direkt verbunden} \}$ ist die Menge der Nachbar- bzw. Kandidatenknoten zur Erweiterung von $T$. Aus $NK$ wird jeweils der Knoten ausgewählt und $T$ hinzugefügt welcher die kürzeste entfernung zu $s$ hat. (Gieriger Algorithmus)

### Beispiel
1. $s$ beaknnt -> rot einfärben.
![[Dijkstra_1.png]]
2. Knoten $s$ hat die kürzeste Entfernung zu sich selbst -> gelb
	1. Direkte Nachbarn von $s$ entdecken -> rot
	2. Ausgehend von $s$ alle Entfernungen zu allen roten Nachbarn vermerken.
![[Dijkstra_2.png]]
3. Knoten $b$ hat die kürzeste Entfernung von $s$ -> gelb.
	1. Direkte Nachbarn $c,f$ -> rot.
	2. Ausgehend von $b$ kürzeste Entfernung in allen roten Nachbarnn Vermerken ($f$ neu $8$)
![[Dijkstra_3.png]]
4.  Knoten $c$ hat die kürzeste Entfernung von $s$ -> gelb.
	1. Direkte Nachbarn $g,z$ -> rot.
	2. Ausgehend von $c$ kürzeste Entfernung in allen roten Nachbarn Vermerken.
![[Dijkstra_4.png]]
5. Knoten $z$ hat die kürzeste Entfernung von $s$ -> gelb.
	1. Direkte Nachbarn $g,d$ -> rot.
	2. Ausgehend von $z$ kürzeste Entfernung in allen roten Nachbarn Vermerken.
![[Dijkstra_5.png]]
6. Knoten $f$ hat die kürzeste Entfernung von $s$ -> gelb.
	1. Direkte Nachbarn $a$ -> rot.
	2. Ausgehend von $f$ kürzeste Entfernung in allen roten Nachbarn Vermerken.
![[Dijkstra_6.png]]
7. Knoten $d,e$ und $g$ haben dieselbe kürzeste Entfernung -> zufällig $d$ gelb.
	1. Keine neuen Nachbarn entdeckt.
	2. Ausgehend von $d$ kürzeste Entfernung in allen roten Nachbarn Vermerken. ($a$ neu $11$)
![[Dijkstra_7.png]]
8. Knoten $e$ und $g$ haben dieselbe kürzeste Entfernung -> zufällig $g$ gelb.
	1. Keine neuen Nachbarn entdeckt.
	2. Ausgehend von $g$ kürzeste Entfernung in allen roten Nachbarn Vermerken.
![[Dijkstra_8.png]]
9. Knoten $e$ hat die kürzeste Entfernung von $s$ -> gelb.
	1. Keine neuen Nachbarn entdeckt.
	2. Ausgehend von $e$ kürzeste Entfernung in allen roten Nachbarn Vermerken.
![[Dijkstra_9.png]]
10.  Knoten $a$ hat die kürzeste Entfernung von $s$ -> gelb.
	1. Keine neuen Nachbarn entdeckt.
	2. Ausgehend von $a$ kürzeste Entfernung in allen roten Nachbarn Vermerken.
![[Dijkstra_10.png]]
=> Keine neuen Nachbarn mehr -> **ENDE**

Die Kürzesten Pfade liefern einen [[Graph#Spanning Tree|Spanning Tree]]:
![[Dijkstra_SpanningTree.png]]

## Analyse
Im Wesentlichen muss $|V|$ mal der nächste Knoten $x$ mit der minimalen Entfernung zu $s$ bestimmt werden.
Der Kandidat dafür ist immer eine Nachbarknoten. **Wesentlich** für die [[AD/Algorithmen/Komplexität|Laufzeit]] ist die [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]] in wlcher die Nachbarknoten verwaltet werden:
- Liste -> $O(|V|^{2})$
- binäräer [[Heap]] -> $O((|V|+|E|) \times \log|V|)$
- Fibonacci Heap -> $O(|E|+|V| \times \log|V|)$

## Invarianten
Die Korrektheit des Algrotihmus basiert auf dem **Invarianzprinzip**. Folgende **Invariante** gilt VOR _und_ NACH einem jeden Erweiterungsschritt:
- VOR: $\forall x\in T$ ist `minEntf[x]` die kürzeste Entferungn von $s$ nach $x$
Schritt: Finde $k \in T$ und $nk \in (V/T)$ mit (`minEntf[k] + f(k, nk))` ist minimal.
- NACH: $\forall x \in T \cup \{ nk \}$ ist `minEntf[x]` die kürzeste Entfernung von $s$ nach $x$.

Via $nk'$ küruzer? Wäre die Entfernung von $s$ via $k'$ und $nk'$ nach $nk$ kürzer, dann müsste auch jene von $s$ nach $nk'$ kleiner sein, und statt $nk$ hätte man $nk'$ gefunden.


## Implementation
```java
public int dijkstra(int s, int z) {
	boolean setT = new boolean[numNodes];
	for (int i = 0; i < numNodes; i++) {
		setT[i] = false;
	}

	setT[s] = true;
	int[] minEntf = new int[NumNodes];
	mintEntf[s] = 0;

	while (!setT[z]) {
		int min = Integer.MAX_VALUE;
		int kNeu = 0;

		for (int k = 0; k < numNodes; k++) {
			if (setT[k]) {
				for (int nk = 0; nk < numNodes; nk++) {
					if(!setT[nk] && (adajMx[k][nk] < Integer.MAX_VALUE)) {
						int kNeuEntf = minEntf[k] + adjaMx[k][nk];
						if (kNeuEntf < min) {
							min = kNeuEntf;
							kNeu = nk;
						}
					}
				}
			}
		}
		setT[kNeu] = true;
		minEntf[kNeu] = min;
	}
	return minEntf[z];
}
```
