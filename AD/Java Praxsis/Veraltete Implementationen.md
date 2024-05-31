Es kursieren immer wieder Hinweise dass die [[AD/Datenstrukturen/Datenstruktur|Datenstrukturen]]:
- `java.util.Stack`
- `java.util.Vector`
- `java.util.HashTable`
nicht mehr verwendet werden sollen, da sie alt und langsam sind.

Diese Strukturen sind in der Tat alt (seit Java 1.0) jedoch sind sie etwas langsamer da sie [[Synchronized|synchronisiert]] sind.

Neuer Datenstrukturen sind darum nicht mehr synchronisiert können aber über eine Wrapper-Klasse syncrhonisiert werden:
```java
final List<Person> list = Collections.synchronizedList(new ArrayList<>());
```


## Concurrent vs Synchronized
Synchronisierte [[AD/Datenstrukturen/Datenstruktur|Datenstrukturen]] sind Threadsafe, das bedeutet jedoch noch nicht, dass sie gleichzeitig verwendet werden können.

Klassen, welche den Präfix `Concurrent`tragen, sind in Java mittels atomaren Operationen so geschickt implementiert worden, dass gleichzeitiger Zugriff gewährleistet werden kann.
- `java.util.concurrent.ConcurrentMap<K,V>
- `java.util.concurrent.ConcurrentLinkedDequeue<E>
- `java.util.concurrent.ConcurrentSkipListSet<K,V>
