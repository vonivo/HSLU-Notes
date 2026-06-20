Auch beim Compiliere wird eine Symboltable benötigt. Dabei gibt es in [[Jack]] zwei Arten von diesen Tabellen:
- Class-Level-Table
- Method-Level-Table

**Beispiel**
```java
class Point {
	field int x, y;
	static int pointCount;

	method int distance(Point other) {
		var int dx, dy;
		let dx = x - other.getx();
		let dy = y - other.getx();
		return Math.sqrt((dx*dx) + (dy*dy));
	}
}
```
Sehe die Tabellen so aus:
![[Pasted image 20260620103330.png]]
Die Nummer wird immer bei Einträgen desselben `kind` hochgezählt → Diese kann dann direkt für den Index der [[Virtuelle Speichersegmente|virtuellen Speichersegment]] des [[Hack-VM-Translator|Vm-Translators]] genutzt werden.

Bei der Kompilation wird nun zuerst in der Method-Level-Table gesucht, wird die Variable nicht gefunden, wird dann in der Class-Level-Tabel gesucht.

**Beipsiel**
 `x + dx` würde zu `push this 0; push local 0; add` kompiliert werden.

>[!Info]
>Bei höheren Sprachen welche Scoping untersützten gibt es pro Scope-Level einen eigene Tabelle.



