**Mit Anonymen Klassen**
```java
Collections.sort(words, new Comparator<String>() {
    public int compare(String s1, String s2) {
        return Integer.compare(s1.length(), s2.length());
    }
});
```
**Mit [[Lambdas]]:**
```java
Collections.sort(words,
        (s1, s2) -> Integer.compare(s1.length(), s2.length()));
```
>[!info]
>Die Typen des Lambdas (`Comparator<String>`), seinen [[Parameter]] (`s1` und `s2` sind beides `String`) und dem Return-Wert (`int`) werde nicht explizit angegeben. Diese identifiziert der Compiler mittels **type interference**.
>
>Teilweise müssen Typen trotzdem angegeben werden, wenn dies aber nicht der Fall ist, **sollen Typen weggelassen werden, ausser sie verbessern die Lesbarkeit.**

Damit diese **type interference** funktioniert, dürfen keine **Raw-Types** (`List`) verwendet werden, sondern es muss der **Generic-Type** (`List<String>`) verwendet werden.

## Vorteile
- Lesbarer
- Kein Boilerplate-Code
- Bessere Performance

## Nachteile
- Lambdas haben keinen Name
- Lambdas können nicht dokumentiert werden (d. h. nur Lambdas bis max 3 Zeilen.)
- Limitiert auf Funktionale Interfaces