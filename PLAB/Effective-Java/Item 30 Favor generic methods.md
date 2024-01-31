In Java können [[Methode|Methoden]] sowie [[Klasse|Klassen]] mit einem [[Polymorphie#Parametrisierte Klassen (Generics)|Typ-Parameter]] versehen werden.
Dies sollte auch immer verwendet werden um auf die Raw-Types zu verzichten:
**No-Go:**
```java
public static Set union(Set s1, Set s2) {
    Set result = new HashSet(s1);
    result.addAll(s2);
    return result;
}
```
**Go:**
```java
public static <E> Set<E> union(Set<E> s1, Set<E> s2) {
    Set<E> result = new HashSet<>(s1);
    result.addAll(s2);
    return result;
}
```
>[!info]
>Bei statischen [[Methode|Methoden]] wird der Type-Parameter vor den Return-Type gesetzt.