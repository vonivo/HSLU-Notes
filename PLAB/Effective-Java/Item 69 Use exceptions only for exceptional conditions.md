[[Exceptionhandling|Exceptions]] sollten nie zweckentfremdet werden wie im Folgenden Beispiel:
```java
try {
    int i = 0;
    while(true)
        range[i++].climb();
} catch (ArrayIndexOutOfBoundsException e) {
}
```
Was passiert, wenn jetzt eine `ArrayIndexOutOfBoundsException` geworfen wird die nichts mit dem Array `range` zu tun hat?
Besser: 
```java 
for (Mountain m : range) {
    m.climb();
}
```



Einerseits wird der Code dadurch **unleserlich** und andererseits bietet das Zweckentfremden folgende **Nachteile:**
- [[Exceptionhandling|Exceptions]] sind für Ausnahme zustände (**langsam**), daher kein grosses Interesse von JVM Entwickler diese schnell extrem schnell zu machen.
- Code innerhalb von `try {} catch{}` **verhindert gewisse JVM-Optimierungen**
- Im obigen Beispiel braucht der Loop mit der Exception etwa 2x so lange.
- **Schwierig zu Debuggen**

>[!info]
>Eine API sollte nie dem Client dazu zwingen [[Exceptionhandling|Exceptions]] für den Controlw-Flow des Programms zu benutzen.
>Wenn der State eines Objekts entscheidend ist, damit eine [[Methode]] fehlerfrei ausgeführt werden kann, soll dafür eine `state-testing`-[[Methode]] zur Verfügung stehen. (Bsp. `iterator.hasNext()`)
