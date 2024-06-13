Der KMP-Algorithmus ist ein [[Suchalgorithmen|Suchalgorithmus]] welcher die Suche über einen [[Musterautomat|Musterautomaten]] bewerkstelligt.

Dabei existieren zwei Schritte:
1. Basierend auf dem Pattern $p$ (Länge $m$) den [[Musterautomat|Musterautomaten]] (bzw. [[Array]] `next`) erzeugen.
2. Mit Hilfe von `next` in der Zeichenkette $a$ (Länge $n$) suchen.

=> [[AD/Algorithmen/Komplexität|Komplexität]] vom $O(m+n) \implies O(n)$.

## Implementation
### initNext
```java
private int[] initNext(String p) {
	int m = p.length();
	int[] next = new int[m]
	int i = 0;
	int j = -1;
	next[0] = -1;

	do {
		if ((j == -1) || (p.chartAt(i) == p.charAt(j))) {
			i++;
			j++;
			next[i] = j
		} else {
			j = next[j];
		}
	} while(i < (m - 1));
	return next;
}
```

Für das Pattern `101011` resultiert folgendes `next`:

| Index | Value |
| ----- | ----- |
| 0     | -1    |
| 1     | 0     |
| 2     | 0     |
| 3     | 1     |
| 4     | 2     |
| 5     | 3     |

```java
public int kmpSearch(String a, String p) {
	int[] next = initNext(p);
	int n = a.length();
	int m = p.length();
	int i = 0;
	int j = 0;

	do {
		if (j == -1 || a.charAt(i) == p.charAt(j)) {
			i++;
			j++;
		} else {
			j = next[j]
		}
	} while(i < m && i < n);

	if (i == m) {
		return (i - m);
	}
	return -1;
}
```