# Definition
Ein Immutable Object ist ein Objekt, bei dem die [[Attribut|Attribute]] nicht mehr verändert werden können. Sprich der State des Objekts kann nach der Objekterstellung nicht mehr geändert werden.

## Eigenschaften
- Keine Set-Methoden
- Private [[Attribut|Attribute]]
- Finale Attribute
- Keine Referenz auf Mutable Objects werden "veröfentlicht"
- [[Klasse]] kann nicht [[Vererbung|verberbt]] werden

# Vorteile:
1. **Immutable Objects are simple**: 
	Immutable Objects sind in dem Sinne einfach, da sich der Zustand des Objekts nicht verändern kann, es kann als kein unvorhergesehener Zustand des Objekts über eine "mutator-Method" erzeugt werden, d. h. einfach in der Benutzung

2. **Immutable Objects are inherently thread-safe; they require no synchronization**
	Da immutable Objects nicht verändertert werden können, sind sie d. h. auch Thread-safe und müsse nicht synchronisiert werden.
	Darum sollten solche Objekte wiederverwendet werden und gängige Objekte als Konstanten zur verfügung gestellt werden.

3. **Immutable Objects can share their internals**
	Weil diese Objekte nicht verändert werden können, kann ein Immutable Object seine mutable [[Attribut|Attribute]] mit an anderen Objekten derselben Klasse teilen.
		**BigInteger** speichert einerseits das Vorzeichen einer Zahl als int sowie den Betrag als int-Array. Wenn nun ein BigInteger negiert wird, wird eine neues Object erzeugt welches ein anderes Vorzeichen hat, aber auf genau dasselbe Array referenziert (Wird wiederverwendet.)

4. **Immutable Objects make great building blocks for other objects**
	Immutable Objekte eignen sich gut für Map-Keys und in Sets, da sie sich nicht verändern werden und somit die Semantik immer einhalten.

5. **Immutable objects provide failure atomicity for free**
	Da immutable Objects nicht verändert werden, können sie auch nach einem Fehler kein Korrupter zustand annehmen.

## Nachteile
- Speicherintensiv
- Rechenintensiv

Da immutable Objects nicht verändert werden können, wird jedes Mal eine neue instant des Objekts mit dem neuen Zustand erstellt. Dies kann dazu führen dass extrem viele Objekt erzeugt werden welche nur als "Zwischenresultat" benötigt werden.
Ist das der Fall, ist oft eine mutable "Companion-Class" wie z.B. StringBuilder sinnvoll.

Beispiel:
```java
String a = "Hello";
String b = "World";

System.out.println(a + " " + b + "!");
```
In diesem Beispiel wird zuerst ein neues String Objekt erstellt, welches "Hello " beinhaltet und danach noch ein Objekt welches "Hello World" enthält und am Schluss noch eins welches "Hello World!" enthält. Es werden 2 ungenutzte Objekt erstellt nur für die Zwischenresultate. Dies kann z.B. mit dem StringBuilder verhindert werden.