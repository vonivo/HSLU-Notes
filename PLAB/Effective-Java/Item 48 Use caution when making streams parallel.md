[[Streams]] können ganz einfach mittels `.parallel()` parallel gemacht werden.
Dies funktioniert jedoch nicht immer so gut.
>[!warning]
>Parallele [[Streams]] mit `.limit()` oder wenn die Source von `Stream.iterate` kommt.

Paralelle [[Streams]] können vor allem bei:
- `ArrayList`
- `HashMap`
- `HashSet`
- `ConcurrentHashMap`
- `int`-Ranges
- `long`-Ranges
- `arrays`
Verbesserungen in der Performance bringen. Diese Datentypen können genau und kosteneffizient in `sub-ranges` aufgeteilt werden. Dies passiert über den **`spliterator`**.
Auch liegt es daran, dass diese Datentypen eine gute **locality of reference** haben. Denn dann werden die Daten miteinander in den Cache des Threads gelesen.

Parallele [[Streams]] können zu:
- livenss failures
- safety failures (z. B. falsche Resultate)
führen.

Dammit sich die Parallelisierung lohn sollte die **Anzahl Elemente mal die Anzahl an Zeilen Code** über **100'000** ergeben. 

