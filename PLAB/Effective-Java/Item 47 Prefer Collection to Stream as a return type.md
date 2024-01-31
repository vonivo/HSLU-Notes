Wenn bei [[Methode|Methoden]] der Rückgabe-Typ vom Typ `Stream` ist, kann danach nicht so einfach über diesen imperativ iteriert werden. Es braucht einen unschönen Workaround, weil das [[Interface]] `Stream<T>` das [[Interface]] `Iterable<T>` nicht erweiterter.

```java
for  (ProcessHandle ph : (Iterable<ProcessHandle>)
                        ProcessHandle.allProcesses()::iterator) {...}
```
Da dieser Code jedoch etwas undurchsichtig ist, wäre es besser eine Adapter [[Methode]] zu schreiben.
```java
public static <E> Iterable<E> iterableOf(Stream<E> stream) {
    return stream::iterator;
}

for (ProcessHandle p : iterableOf(ProcessHandle.allProcesses())) {
    // Process the process
}
```

Falls der Return-Type nur ein `Iterable` ist, kann daraus wiederum nur ein Stream über eine Adapter-[[Methode]] erstellt werden:
```java
public static <E> Stream<E> streamOf(Iterable<E> iterable) {
    return StreamSupport.stream(iterable.spliterator(), false);
}
```

>[!info]
>Bei einer öffentlichen API sollte immer ein `Collections`-[[Interface]] zurückgegeben werden, da es vom Typen `Iterable` ist und eine `.stream()`-[[Methode]] zur Verfügung stellt.

Wenn eine Collection so gross ist, dass unmöglich eine zweite davon erstellt werden kann, kann man darüber nachdenken eine **eigene Collection** zu erstellen oder ein **Stream** zurückzugeben.