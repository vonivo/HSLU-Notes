Simple Search [[Suchalgorithmen|sucht]] die Zeichenkette schrittweise von vorn nach hinten durch.

## Ablauf
1. Überprüfe an jeder Stelle, ob das Pattern vorkommt.
	- Falls ja, gib den entsprechenden Index zurück.
	- Falls nein, gehe einen Schritt weiter.
2. Falls das Pattern nirgends auftaucht gib $-1$ zurück.

=> Das Pattern wird Schritt für Schritt durch die Zeichenkette verschoben.
![[SimpleSearch.png]]

## Implementation
```java
public int search(String a, String p) {
	int maxIndex = a.length - p.length;
	for(int i = 0; i  < maxIndex, i++) {
		boolean success = false;
		for(int j = 0; j < p.length; j++) {
			if (a.charAt(i + j) != p.charAt(j)) {
				success = false;
				break;
			}
		}

		if (success) {
			return i
		}
		i++;
	}
	return -1;
}
```

## Analyse
**Worstcase**
Im Worstcase kommt das Pattern $p$ nicht in der Zeichenkette $a$ vor, aber es muss trotzdem $m$ vergleichen werden. 

a: "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaa..."
b: "aaaaab"

Also muss das Pattern insgesamt $n-m$ mal geschoben werden.

=> [[AD/Algorithmen/Komplexität|Komplexität]] vom $O((n-m)*m) = O(n*m-m*m) \implies O(n*m)$

**Averagecase**
Im AvergaceCase wird die durchschnittliche Anzahl Zeichenvergleiche pro Stelle durch die Häufigkeit der Zeichen limitiert. Je grösser das Alphabet, desto schneller.
=> [[AD/Algorithmen/Komplexität|Komplexität]] vom $O(n)$

=> Dieser Algorithmus sucht systematisch und stur => **Brute Force**
=> Ein Zeichen in a muss mehrmals verglichen werden.
