**Bedingungen**
- Rückgabe ist identisch bei gleichen Argumenten
	- Keine Einflüsse durch Variablen
	- Keine Einflüsse durch Argumenttyp (Referenz oder Wert)
	- Keine Einflüsse durch I/O
- Funktion hat keine Nebeneffekte
	- Keine Modifikation von Variablen außerhalb des Scopes
	- Keine Modifikation von als Referenz übergebene Argumente
	- Keine Modifikation von I/O Streams.

## Beispiel
```java
public class SomeClase {
	private static final Collection<Integer> resultList = new ArrayList();

	public static impureAdd(int a, int b) {
		var res = a + b;

		// impure, function has side effect, modifies variable out of function scope
		resultList.add(res);

		// Impure, I/O-Stream modification
		System.out.println("Summ of a and b is :" + res);

		return res;
	}

	public static int pureAdd(int a, int b) {
		return a + b;
	}
}
```
