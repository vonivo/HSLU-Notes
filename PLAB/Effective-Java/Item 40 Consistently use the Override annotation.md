Mit der Annotation `@Override` können Funktionen annotiert werden, welche eine Funktion von einem Supertypen überschreibt. Dies kann einem vor vielen mühsamen Bugs schützen.

# Beispiel
```java
class Test {
...
    public boolean equals(Bigram b) {
        return b.first == first && b.second == second;
    }
}
```
Versucht eindeutig die [[Equals & Hashcode#equals|Equals-Methode]] zu überschreiben.
Die Signatur von `Objects.equals` ist jedoch `boolean equals(Object o)`. Dass heisst hier wird die [[Equals & Hashcode#equals|Equals-Methode]] überladen anstatt überschrieben und es immer noch auf die Identität `==` überprüft.

Wenn nun diese Methode mit `@Override` annotiert wird. Wird der Compiler folgenden Fehler werfen.
```java
Bigram.java:10: method does not override or implement a method
from a supertype
    @Override public boolean equals(Bigram b) {
```

Diese Annotation sollte auch bei [[Interface|Interfaces]] verwendet werden, da [[Interface|Interfaces]] Default-Implementation haben können.
