Alle Java-Objekte besitzen eine implizite Sperren (Lock).
Den Zugriff auf den Lock erhält man über das Schlüsselwort `synchronized`.

Während des Wartens auf den Lock kann der Thread nicht mit einem [[AD/Nebenläufigkeit/Thread/Interrupt|Interrupt]] unterbrochen werden.

## Beispiel
```java
class SimpleCounter {
	private final Objeckt lock = new Object;
	private int count = 0;

	public int increment() {
		synchronized(lock) {
			count++;
			return count;
		}
	}
}
```

## Lock Objekte
Mit dem `synchronized` Keyword kann ein Lock-Objekt spezifiziert werden. Jedes Objekt besitzt **genau ein Lock**.

- Wird `synchronized` direkt auf einer [[Methode]] verwendet, wird `this`als Lock-Objekt verwendet.
- Wird `synchronized` direkt auf einer statischen [[Methode]] verwendet, wird die Klasse als Lock-Objekt verwendet.

Locks sollten nie exponiert werden, da ansonsten der Lock gebrochen werden kann.