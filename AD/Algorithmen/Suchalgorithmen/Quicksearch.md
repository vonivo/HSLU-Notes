Quicksearch ist ein [[Suchalgorithmen|Suchalgorithmus]] der das schnelle Durchsuchen einer Zeichenkette `a` nach einem Pattern `p`.

Quicksearch wird durch ein Alphabet mit vielen Symbolen begünstigt.

Quicksearch verfolgt den Ansatz, dass möglichst schnell durch die Zeichenkette gesprungen wird.

## Prinzip
1. Das Pattern wird Zeichenweise mit der Zeichenkette verglichen.
	- Bei einer Unstimmigkeit wird das Vergleichen abgebrochen.
	=> Eine potenzielle Fundstelle muss weiter rechts liegen.
2. Als nächste potenzielle Fundestelle wird das Zeichen unmittelbar nach dem Pattern betrachtet. `a[i + m]`
	- Käme diese Fundstelle nicht im Pattern vor, wird ein Schritt weiter gegangen.
![[Quicksearch_1.png]]
3. Das Pattern wird so weit nach rechts geschoben, bis das erste `b` im Pattern mit der Zeichenkette übereinstimmt.
![[Quicksearch_2.png]]
4. Der neue Startpunkt in der Zeichenkette wird mithilfe des Shift-[[Array]] berechnet: `iNeu = iAlt + shift['b']`
### Shift-Tabelle
Mithilfe der Shift-Tabelle lässt sich bestimmen, wie weit das Pattern verschoben werden darf.

Die Shift-Tabelle ist genau so gross wie das Alphabet.

Erstellung:
1. Alle Felder mit `m + 1` initialisieren. (Für Buchstaben, welche nicht im Pattern sind)
2. Alle Zeichen des Patterns durchlaufen und `m-i` überschreiben.

### Wildcards
Quicksearch lässt auch Wildcards zu.
Wildcards müssen bei er suche nicht verglichen werden -> passen schliesslich immer.

=> Das Wildcardzeichen ganz Rechts begrenzt alle Shift-Werte. (Ist ein Wildcard ganz rechts ist der maximale Shift-Wert 1.)

## Analyse
Quicksearch ist ein äusserst schneller Algorithmus.

**BestCase**
Der Bestcase hat eine [[AD/Algorithmen/Komplexität|Komplexität]] vom $O\left( \frac{n}{m} \right)$ und tirtt bei folgender Situation ein:

Zeichenkette: "aaaaaaaaaaaaaaaaaaa"
Pattern:          "bbbb"

**Worstcase**
Im Worstcase kann der Quicksearch zur [[Simple Search]] degenerieren. [[AD/Algorithmen/Komplexität|Komplexität]] vom $O(n*m)$

Zeichenkette: "aaaaaaaaaaaaaaaaaaa"
Pattern:          "aaaaba"

## Implementation
```java
public int search(String a, String p) {
	int n = a.length();
	int m = p.length();
	int range = 256;
	int[] shift = new int[256];

	for (int i = 0; i < range; i++) {
		shift[i] = m + 1;
	}

	for (int i = 0; i < m; i++) {
		shift[p.charAt(i)] = m - i; 
	}

	int i = 0;
	int j = 0;

	do {
		if (a.charAt(i + j) = p.charAt(j)) {
			i++;
			j++;
		} else {
			if (i + m < n) {
				i = shift[a.chartAt(i + j)];
				j = 0;
			} else {
				break;
			}
		}
	} while(j < m && (i + m) <= n)

	if (j == m) {
		return i;
	}

	return -1;
}
```