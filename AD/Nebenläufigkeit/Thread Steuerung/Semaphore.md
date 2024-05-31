Ein Semaphore ist ein Konstrukt der [[Thread]]-Steuerung und verwaltet wie viele Threads eine geschützte Aktion ausführen kann.
Somit ist das Semaphore ein **Zähler** für **Passiersignale**.

Das Semaphore kennt zwei Operationen:
- P -> steht für passieren (passere) / acquire
- V -> steht für erhöhen (verhogen) / release


## Definition
Für ein Semaphore $s$ sei:
- $p$ die Anzahl der abgeschlossenen $P$-Operationen auf $s$
- $v$ die Anzahl der abgeschlossenen $V$-Operationen auf $s$
- $n$ ein Initalwert, der $n$ Passiersignale in $s$ initialisiert

Damit gilt: $s \geq 0 \text{ \&\& } s = n + v - p$

Mit anderen Worten:
- $v$ kann immer ausgeüfhrt werden
- $p$ nur wenn $p\leq v +n$

## Implementation
```java
class Semaphore {
	private final Object lock = new Object();
	private int sema;

	public Semaphore(int n) {
		this.sema = n
	}

	public void acquire() {
		synchronized(lock) {
			while (sema <= 0) {
				lock.wait();
			}
			sema--;
		}
	}

	public void release() {
		synchronized(lock) {
			sema++;
			lock.notifyAll();
		}
	}
}
```

## Anwendung
- Ein Semaphore verwaltet die Ressourcen nicht selbst, sonder steuert nur den Zugriff.
- Werden hauptsächlich in komplexeren Synchronisations-Mechanismen verwendet.
- Bei der Verwendung muss unterschieden werden ob ein:
	- starkes Sempahore: Besitzt eine FIFO-[[Queue]]
	- schwaches Semaphore: Besitzt eine "uncoditionally fair" Pool
	verwendet wird.
	