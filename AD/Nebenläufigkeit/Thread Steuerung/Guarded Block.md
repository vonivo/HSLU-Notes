Wenn das Eintreten in einen kritischen Abschnitt an eine Bedingung geknüpft ist, wird dieser ein **Guarded Block** genannt.
Das heisst, das Nebenläufig auf einen bestimmten Zustand gewartete werden muss, dabei ist **busy waiting** zu Vermeiden.

$\implies$ Signale verwenden.

## Beispiel
```java
public void guard() throws InterruptedException {
	synchronized(lock) {
		while(!joy) {
			lock.wait()
		}
		// do something
	}
}
```
- Das Überprüfen der Bedingung wird **muss** immer in einer **Schleife** gemacht werde, da sich der Zustand [[Nebenläufigkeit und Parallelität|nebenläufig]] ändern kann.
- Wenn die Bedingung nicht zutrifft, wird der [[Thread]] mittels [[Wait|wait()]] in den [[Lebenszyklus eines Threads|Wartemodus]] versetzt.
- Über [[Notify|Benachrichtigungen]] wird der Thread wieder geweckt.
