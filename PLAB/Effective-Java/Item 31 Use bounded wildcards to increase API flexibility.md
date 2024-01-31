In Java sind  [[Polymorphie#Parametrisierte Klassen (Generics)|parameterisierte Typen]] invariant. Das heisst, dass `List<String>` kein Subtypen von `List<Object>` ist.
Darum funktioniert z.B. so etwas **nicht**:
```java
**// pushAll method without wildcard type - deficient!**
public void pushAll(Iterable<E> src) {
    for (E e : src)
        push(e);
}

Stack<Number> numberStack = new Stack<>();
Iterable<Integer> integers = ... ;
numberStack.pushAll(integers);
```
Und wir bekommen folgende Fehlermeldung:
```
StackTest.java:7: error: incompatible types: Iterable<Integer>
cannot be converted to Iterable<Number>
        numberStack.pushAll(integers);
```


Um diesem Problem entgegenzuwirken, gibt es in Java die sogenannten bounded Wildcards `List<? extends E>`
So würde es funktioniere:
```java
public void pushAll(**Iterable<? extends E>** src) {
    for (E e : src)
        push(e);
}
```
Nun funktioniert das ganze.

Angenommen wir wollen jetzt noch eine `popAll(Collection<E> dst)` machen:
```java
public void popAll(Collection<E> dst) {
    while (!isEmpty())
        dst.add(pop());
}

Stack<Number> numberStack = new Stack<>();
Collection<Object> objects = ... ;
numberStack.popAll(objects);
```
haben wir hier wieder dasselbe Problem. Um dies zu Fixen müssen wird anders vorgegehen:
```java
public void popAll(**Collection<? super E>** dst) {
    while (!isEmpty())
        dst.add(pop());
}
```

>[!infor]
>Für maximale Flexibilität sollten immer Wildcard-Typen verwendet werden.


## PECS: Producter-`extends` Consumer-`super`
Das heisst, wenn ein parametrisierter Type `T` einen producer ist, soll `<? extends T>` verwendet werden.
Wenn `T` einen Consumer repräsentiert soll `<? super T>` verwendet werden.

>[!warning]
>In Return-Types sollten keine Wildcards verwendet werden. Das zwingt den Client ebenfalls Wildcards zu benutzen

Falls ein Typparameter `T` nur einmal verwendet wird sollte mit dem Wildcard `?` ersetzt werden.

