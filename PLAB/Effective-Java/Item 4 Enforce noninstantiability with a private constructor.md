Statische Klassen können genutzt werden, um Konstanten, [[Methode|Methoden]] zu gruppieren. **Solche [[Klasse|Klassen]] wurde nicht dazu entworfen, um Instanzen zu erzeugen.**

Diese "noninstantiability" kann nicht über eine [[Abstrakte Klasse]] realisiert werden, da diese [[Vererbung|vererbt]] werden kann.

Eine [[Klasse]] kann "**noninstantiable**" gemacht werden, indem der [[Konstruktor]] auf `private` gesetzt wird:
```java
public class UtilityClass {
    // Suppress default constructor for noninstantiability
    private UtilityClass() {
        throw new AssertionError();
    }
    ... // Remainder omitted
}
```
Dieser Ansatz bietet auch noch die Sicherheit, dass die [[Klasse]] nicht [[Vererbung|vererbt]] wird.