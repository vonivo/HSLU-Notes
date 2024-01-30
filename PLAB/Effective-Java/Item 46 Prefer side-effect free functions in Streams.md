Nach dem [[Streams]]-Paradigma sollten nur Side-Effect free Functions in [[Streams]] verwendet werden. Insbesondere sollte die Terminal-Operation `.foreach()` nur verwendet werden, um das Ergebnis des [[Streams]] zu liefern und nicht um Operationen ausführen.

Um [[Streams]] wirklich zu beherrschen, muss man die verschiedenen Arten von `Collectors`, welche die Elemente am Schluss einsammeln, kennen.
Häufig verwendetet `Collectors`:
- `toList()`
- `toSet()`
- `toMap()`
- `groupingBy()`
- `joining()`


