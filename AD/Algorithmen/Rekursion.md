Rekursion beschreibt den Prozess, wenn dasselbe Problem verschachtelt mit derselben Lösung gelöst wird.

In der Programmierung ist Rekursion eine Funktion, die sich selbst aufruft.

## Eigenschaften
Damit eine Rekursion funktioniert, bracht es eine **Abbruchbedingung**. Diese Abbruchbedingung ist meist die Lösung des einfachsten Problems und wird **Rekursionsbasis** genannt.

Das schwierige Problem wird mit der **Rekursionsvorschrift** in ein gleichartiges einfacheres Problem unterteilt, das wieder vereinfacht wird, bis hin zu der **Rekursionsbasis**.

Beispiel Fakultät
```java
public static int fakultät(int n) {
	if (n <= 1) {             -> Rekursionsbasis
		return 1;
	}

	 return n * fakultät(n - 1);   -> Rekusionsvorschrift
}
```

## Mächtigkeit
- Die Rekursion praktisch gleich mächtig wie die Iteration.
- Eine rekursive Implementation lässt sich grundsätzlich immer in eine gleichwertige iterative Implementation umprogrammieren und umgekehrt.
- Jedoch benötigt die Iteration deutlich mehr Speicher, weil alle Aufrufe auf den [[Call-Stack]] gelegt werden und daher auch langsamer.

## Vorteile
- mächtiges Lösungskonzept
- häufig einfache und elegante Problemlösung
- weniger Quellcode
- Korrektheit häufig einfacher zu zeigen

## Nachteile
- schnell sehr viele Methodenaufrufe
- tendenziell langsamere Programmausführung
- grosser Speicherbedarf

## Beispiel
Ein gutes Beispiel ist die Fibonacci-[[Reelle Zahlenfolgen|Folge]]. 
$$
\begin{align}
f_{0} &= 0 \\
f_{1} &= 1 \\
f_{n} &= f_{n-1} + f_{n-2}
\end{align}
$$
Dies kann extrem einfach rekursiv implementiert werden.
Das Problem dabei ist jedoch, dass viele Zahlen doppelt berechnet werden:
![[Fibonacci.png]]
Die [[Komplexität]]-Klasse der Aufrufe entspricht hier $O(2^{n})$.


## Rekursionstypen
Direkte Rekursion ist eine Methode welche sich **direkt** selbst aufruft.

Eine Indirekte Rekursion ist eine rekursive Methode, welche sich nur indirekt aufruft:
```java
public static boolean isOdd(final int n) {
	if (n == 0) {
		return false;
	} else {
		return isEven(n - 1);
	}
}

public static boolean isEven(final int n) {
	if (n == 0) {
		return true;
	} else {
		return isOdd(n - 1);
	}
}
```

### Lineare Rekursion
Die Ausführung der Methode $m(\dots)$ führt zu **höchstens einem** rekursiven Aufruf.
-> **primitiv rekursiv**
$m(\dots) \to m(\dots)$
z.B. Fakultät

### Nichtlineare Rekursion
Die Ausführung der Methode $m(\dots)$ führt zu **mehr als einem** rekursiven Aufruf.

- **nicht geschachtelt**, ->d. h. **primitiv rekursiv**
	$m(\dots) \to m(\dots), m(\dots)$
	z.B. Fibonacci
- **geschachtelt**, d.h. -> **nicht primitiv rekursiv**
	$m(\dots) \to m(m(\dots)\dots)$

