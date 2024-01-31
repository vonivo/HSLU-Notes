Um einen Sigleton zu implementieren, existieren zwei Varianten. Beide basieren auf einem `private` [[Konstruktor]] und einem `public static` [[Attribut]].

## Variante 1
In einem Ansatz ist das [[Attribut]] `final`:
```java
public class Elvis {
    public static final Elvis INSTANCE = new Elvis();
    private Elvis() { ... }

    public void leaveTheBuilding() { ... }
}
```
Bei dieser Variante kann der private [[Konstruktor]] über Reflexion trotzdem noch aufgerufen werden. Der [[Konstruktor]] kann jedoch so implementiert werden, dass er eine Exception ruft, falls dies passiert.

### Vorteile
- API macht klar, dass die [[Klasse]] ein Singleton ist.
- Einfach

## Variante 2
```java
// Singleton with static factory
public class Elvis {
    private static final Elvis INSTANCE = new Elvis();
    private Elvis() { ... }
    public static Elvis getInstance() { return INSTANCE; }

    public void leaveTheBuilding() { ... }
}
```

### Vorteile
- [[Klasse]] kann in ein Nicht-Singleton umgewandelt werden, ohne die API zu ändern.
- Es kann eine `generic singleton factory` implementiert werden.
- Methodenreferenz kann als Supplier genutzt werden.


## Serialisierung
Um eine Singleton richtig zu Serialisieren muss die [[Methode]] `readResolve()` wie folgt implementiert werden:
```java
// readResolve method to preserve singleton property**
private Object readResolve() {
     // Return the one true Elvis and let the garbage collector
     // take care of the Elvis impersonator.
    return INSTANCE;
}
```

## Variante 3
Ein Singleton kann auch über ein [[Enum]] erstellt werden:
 ```java
 // Enum singleton - the preferred approach
public enum Elvis {
    INSTANCE;

    public void leaveTheBuilding() { ... }
}
```
Diese Variante ist ähnlich zu Variante 1, stellt aber die Serialisierung gratis zur Verfügung und ist verständlicher. Diese Variante kann aber nicht mit [[Vererbung]] kombiniert werden.