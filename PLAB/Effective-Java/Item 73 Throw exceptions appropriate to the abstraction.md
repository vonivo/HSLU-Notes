Es kann sein, dass gewisse Methoden eine [[Exceptionhandling|Exception]] werfen, welche eigentlich nichts mit der eigentlichen Aufgabe der [[Methode]] zu tun hat. 
Dies kommt davon, dass diese (higher-level) [[Methode]] [[Exceptionhandling|Exceptions]] von verschachtelten (lower-level) Aufrufen einfach weiterleitet. (**Verschmutzt die API, da es Implementationsdetails bekannt gibt. (kein [[OOP/Kopplung#Information Hiding|Information Hiding]]**)

Wenn nun die **Implementation High-Level-API** geändert wird, ändern sich potenziell auch die [[Exceptionhandling|Exceptions]], was danach eine Änderung im Client verursacht.
## Exception Translation
High-Level-Layers sollten [[Exceptionhandling|Exceptions]] von Lower-Leves catchen und dann eine neue [[Exceptionhandling|Exception]] werfen, welche in der High-Level-Abstraktion erklärt werden kann.

```java
try {
    ... // Use lower-level abstraction to do our bidding
} catch (LowerLevelException e) {
    throw new HigherLevelException(...);
}
```

### Exception Chaining
Wenn die Low-Level-Exception vielleicht nützlich sein kann für den Entwickler kann sie der High-Level-Exception mitgeben werden als `cause`.
```java
try {
    ... // Use lower-level abstraction to do our bidding
} catch (LowerLevelException cause) {
    throw new HigherLevelException(cause);
}
```
Dies wird über den `chaining-aware constructor` gemacht, welcher die Exception biss hinauf zu `Throwable` leitet.
Wenn kein solcher [[Konstruktor]] zur Verfügung steht kann dies über die [[Methode]] `initCause` gemacht werden.

**Exceptions-Translations sollte nich überbenutzt werden,** das Beste ist, wenn die Low-Level-Exception so gehandelt wird, dass die High-Level-Funktion trotzdem funktioniert.