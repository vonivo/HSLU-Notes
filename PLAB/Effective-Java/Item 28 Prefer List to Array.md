Arrays in Java sind **kovariant** (im Gegensatz zu [[Item 31 Use bounded wildcards to increase API flexibility|Generic Types]]). Das bedeutet, dass wenn der Typ `Sub` ein Subtyp von `Super` ist, ist das Array `Sub[]` ein Subtyp von `Super[]`.

Dieser Umstand täuscht einen Vorteil vor, denn folgender Code erzeugt kein Kompilierfehler, sondern ein **Laufzeitfehler**:
```java
// Fails at runtime!
Object[] objectArray = new Long[1];
objectArray[0] = "I don't fit in"; // Throws ArrayStoreException
```
Im gesegensatz zu Generic-Types welches ein Kompilerfehler erzeugt:
```java
// Won't compile!**
List<Object> ol = new ArrayList<Long>(); // Incompatible types
ol.add("I don't fit in");
```

Ein zweiter Unterschied ist, dass Arrays *reified* sind. Heisst sie forcieren ihre Element-Typen zur Laufzeit (Bei Generic-Types wird es nur zur Compile-Time gemacht (Typeerasure))

>[!warning]
>Es darf kein Array über einen generischen Typen, eine parametrisierten Typen oder eine Typ-Parameter erzeugt werden.


## Vorteile
- Bessere **Typsicherheit** (Ansonsten muss immer explizit gecastet werden -> potenzial für `RuntimeExceptions`)
- Bessere **Interoperabilität**

## Nachteile
- Eventueller Performanceverlust
