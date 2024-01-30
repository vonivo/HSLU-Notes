Bekanntlich gibt es in Java einmal die primitiven Datentypen wie `int, double, etc.` und die sogenannten Boxed-Primitives `Double, Integer, etc.`. Das "auto-unboxing" hilft dabei, die Boxed-Primitives in primitives umzuwandeln.

>[!info]
>Wo immer möglich sollten primitive Datentypen verwendet werden, da diese effizienter sind und weniger potenzial für Fehler bringen.



## Unterschied
1. Primitive Datentypen besitzen nur ihren Wert, wobei Boxed-Primitives eine Identität unterschiedlich zu ihrem Wert besitzen. Dies führt dazu, dass sie den **gleichen Wert** haben können, aber eine **unterschiedliche Identität**.
2. Primitive Datentypen haben nur voll funktionsfähige Werte. Boxed-Primitives besitzen auch noch den Wert `null`.
3. Primitive Datentypen sind viel Speicher- und Zeiteffizienter.

## Probleme mit Boxed-Primitives
1. Bei `==`-Operator wird die [[Equals & Hashcode#1. Identität (Entity Types)|Identiät]] anstatt die [[Equals & Hashcode#2. Wertegleichheit (Value Types)|Wertegleichheit]] überprüft. (kein Auto-unboxing)
```java
Comparator<Integer> naturalOrder =
    (i, j) -> (i < j) ? -1 : (i == j ? 0 : 1);
```

Darum funktioniert dieser Comparator nicht. Da bei `i == j` nicht die Werte verglichen werden sonder die [[Equals & Hashcode#1. Identität (Entity Types)|Identiät]].

2. Beim Auto-Unboxing kann eine  `NullPointerException` geworfen werden.
```java
public class Unbelievable {
    static Integer i;

    public static void main(String[] args) {
        if (i == 42)
            System.out.println("Unbelievable");
    }
}
```
Dieser Code produziert eine `NullPointerException`, da versucht wird `i` welcher `null` ist in einen `int` zu boxen.

3. Konstantes unnötiges Boxing -> verschlechtert Performance massiv
```java
public static void main(String[] args) {
    Long sum = 0L;
    for (long i = 0; i < Integer.MAX_VALUE; i++) {
        sum += i;
    }
    System.out.println(sum);
}
```
Hier wird der `Long sum` immer wieder geboxt (bei `sum += i`), was die Performance extrem verschlechtert.