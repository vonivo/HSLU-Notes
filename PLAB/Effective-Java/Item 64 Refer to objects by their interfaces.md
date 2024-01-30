Wenn ein passendes [[Interface]] existiert, sollte dies für die Deklaration von [[Parameter]], [[Attribut|Attribute]] und [[Lokale Variable|Variablen]] verwendet werden.

**Gut:**
```java
Set<Person> personSet = new LinkedHashSet<>();
```
**Schlecht:**
```java
LinkedHashSet<Person> personSet = new LinkedHashSet<>();
```

Wenn [[Interface|Interfaces]] als Typen benutzt werden, wird das Programm dadurch viel **flexibler**.
Nun kann z. B. die spezifische Implementation von `Set<Person> personSet` ausgetauscht werden, ohne dass sonst noch etwas geändert werden muss.




## Ausnahmen

1. **Falls kein passendes [[Interface]] existiert**(z.B. für Value-Types wie String) ist es **vollkommen in Ordnung** die [[Klasse]] als Typ zu verwenden.
2. Falls eine Library verwendet wird, welche ein `class-based-framework` ist, sollte die entsprechende **Basis Klasse** verwendet werden, welche in der Regel [[Abstrakte Klasse|abstrakt]] ist.
3. Falls eine Funktion benötigt wird, welche die spezifische Implementation zur Verfügung stellt, dass [[Interface]] jedoch nicht

Wenn es kein [[Interface]] gibt, sollte die am wenigsten speziefischte [[Klasse]] benutzt werden.

