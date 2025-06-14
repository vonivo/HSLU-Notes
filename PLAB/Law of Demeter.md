Die Law of Demeter besagt, dass Objekte nur zu Freunden und nicht zu Unbekannten sprechen soll.

Durch diese Regel wird verhindert, dass Objekte ihre interne Struktur über Accessor-Methoden exponieren, was dem [[OOP/Kopplung#Information Hiding|Information Hiding]] widerspricht.

Dass heisst:

Die [[Methode]] `f` der [[Klasse]] `C` darf nur Methoden:
```java
class C {
	...
	public void f (....) {
	...
	}
}
```
- von der [[Klasse]] C
- von Objekten welche in der [[Methode]] `f` erzeugt werden
- von Parametern
- von Instanzvariablen von der [[Klasse]] `C`
aufrufen.

Die Methode `f` soll keine Methoden von Objekten aufrufen, welche `f` als Rückgabewert von irgendeiner Methode erhält aufrufen.