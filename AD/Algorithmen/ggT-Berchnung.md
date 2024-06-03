Der [[Algorithmus]] zu Berechnung des ggT von zwei Zahlen $A$ und $B$ funktioniert wie folgt:

1. Sei $A$ die grössere der beiden Zahlen. (vertauschen falls nicht der Fall)
2. $A = A -B$
3. Wenn neues $A$ und $B$ ungleich sind, mit 1. fortfahren, ansonsten ist $A$ das ggT

## Iterative Implementation
```java
public static int ggT(int a, int b) {
	while (a != b) {
		if (a > b) {
			a = a - b;
		} else {
			b = b - a;
		}
	}
	return a
}
```

Mit dem Modulo Operator wird der Algorithmus extrem effizienter:
```java
public static int ggT(int a, int b) {
	while (a != 0 && b != 0) {
		if (a > b) {
			a = a % b;
		} else {
			b = b % a;
		}
	}
	return a + b;
}
```

## [[Rekursion|Rekursive]] Implementation
```java
public static int ggT(int a, int b) {
	if (a == b) {
		return a;	
	}
	
	if (a > b)
		return ggT(a - b, b);
	else
		return ggT(a, b - a);
}
```

Alle Implementationen basieren auf Euklid, verwenden aber:
- unterschiedliche Ansätzen Schleifen vs Rekursion
- Abkürzung mit Modulo

Daher unterscheidet sich die [[AD/Algorithmen/Komplexität|Laufzeitkomplexität]] der Algorithmen so wie der Speicherbedarf.