Abstrakte [[Klasse|Klassen]] und [[Interface|Interfaces]] erlauben das zur Verfügung stellen von Default-Implementationen. Der Hauptunterschied dabei ist, dass eine [[Klasse]] welche, welche den Typ der Abstrakten-[[Klasse]] hat, auch von dieser [[Vererbung|Erben]] muss. Da Java nur einfache [[Vererbung]] kennt, ist dies ein erheblicher Nachteil gegenüber [[Interface|Interfaces]].

Wenn ein [[Interface]] hinzugefügt wird, ist es für [[Klasse|Klassen]] einfach im Nachhinein dieses [[Interface]] zu implementieren. Soll im Nachhinein eine Abstrakte-[[Klasse]] erweitert werden, ist dies ziemlich schwierig, da die Typ-Hierarchie verfälscht wird.

Interfaces ermöglichen eine zusätzliche Funktion zu implementieren wie z. B. das `Comparable<T>` [[Interface]]. (**Mixin**)

Ausserdem können mit [[Interface|Interfaces]] 'non-hierarchiche'-Typsysteme gebaut werden. (z. B. `Singer`, `Songwriter` und `SingerSongwriter`.)

Am besten funktioniert Interfaces mit einer sogenannte `SekeletalClass`, einer Abstrakte-[[Klasse]] welche schon Basisimplementierungen vornimmt, welche nicht über die Default-Implementation gemacht werden können. Dies erlaubt Programmierer dass einfache Benutzen dieser Klasse (Bsp. `List<>` und `AbstractList<>`).

## Vorteile
- Erlaubt "mehrfach Implementation"
- Kann im Nachhinein hinzugefügt werden
- Erlaubt zusätzliche Funktionen (mixin)
- Erlaubt 'non-hierarchiche'-Typsysteme
- Kann mit `SkeletalClass` kombiniert werden.

