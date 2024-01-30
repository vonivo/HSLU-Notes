Methodenreferenzen können [[Lambdas]] teilweise ersetzen.
**Beispiel**
```java
map.merge(key, 1, (count, incr) -> count + incr);
```
wird zu
```java
map.merge(key, 1, Integer::sum);
```


## Vorteile
- Weniger, und klarerer Code
- Können zu grosse [[Lambdas]] ersetzen (kann in Funktion ausgelagert werden.)

## Arten von Methoden Referenzen
| Type | Beispiel | Lambda |
| ---- | ---- | ---- |
| static | `Integer::parseInt` | `str -> Integer.parseInt(str)` |
| bound | `Instant.now()::isAfter` | `Instant then = Instant.now();`<br>`t -> then.isAfter(t)` |
| unbound | `String::toLowerCase` | `str -> str.toLowerCase()` |
| class constructor | `TreeMap<K,V>::new` | `() -> new TreeMap<K,V>()` |
| Array Constructor | `int[]::new` | `len -> new int[len]` |
