Bei der Komplexität eines [[Algorithmus]] wird unterschieden, wie viel Zeit er benötigt (**Laufzeitkomplexität**) und wie viel Speicher benötigt wird (**Speicherkomplexität**).

Die Komplexität ist daher immer **abhängig** von den **Eingabedaten** (Grösse und Anzahl der Daten).

Bei der Komplexität ist die absolute Zeitmessung nebensächlich. Wichtig ist, wie der Ressourcenbedarf wächst** (z.B. bei einer Verdoppelung der Daten).

## Beispiel
```java
public static void task(final int n) {
	task1();task1();task1();task1();
	for (int i = 0; i < j; i++) {
		task2();task2();task2();
		for (int j = 0; j < n; j++) {
			task3();task3();
		}
	}
}
```
Task 1-3 benötigen etwa alle 1 Zeiteinheit.

Daher benötigt die [[Methode|Funktion]] allgemein:
$$
\begin{align}
T = f(n) &= 4 * 1 + n(3*1+n(2 * 1)) \\
&=4+n(3+2n) \\
&=4+3n+2n^2
\end{align}
$$**Je grösser n** desto **dominanter** wird $n^2$. Sprich $n^2$ wächst im Verhältnis viel schneller als $4+3n$.
Daher ist die Laufzeitkomplexität (Ordnung) im Sinne der [[Big-O-Notation]] $O(n^{2})$.