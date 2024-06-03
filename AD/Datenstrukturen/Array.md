Ein Array ist eine **geordnete**, **statische** [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]], welche **direkten Zugriff** erlaubt.

## Beispiel
![[Array_full.png]]
- Das Array ist voll (jede Stelle ist belegt)
- Die Daten im Array sind sortiert vorhanden.

![[Array_partiallyfull.png]]
- Das Array hat noch vier freie Plätze
- Elemente sind weder sortiert noch fortlaufend.
**Empfehlung**: Arrays sollten immer so befüllt werden, dass freie Plätze möglichst vermieden werden.

## Eigenschaften
- **Statisch**: Grösse wird bei Initialisierung festgelegt. `char demo = new char[8`
- **Implizit**: Die einzelnen Elemente habe keine Beziehung zueinander.
- **Direkter Zugriff**: Auf jedes Element kann mittels des Index direkt zugegriffen werden.
- **Geordnet**: Das Array behält die Positionen der Datenelemente

## Suchen
**Fall 1**
Daten sind **nicht sortiert**, aber **fortlaufend** befüllt.
Das Array kann nun sequenziell durchsucht werden mit der [[AD/Algorithmen/Komplexität]] von $O(n)$.
![[linearSearch.png]]
**Fall 2**
Daten sind **sortiert** und **fortlaufend**.
Mit der [[Binäre Suche|binären Suche]] kann das Array durchsucht werden.

## Anhängen & Einfügen
**Fall 1**
Daten **nicht sortiert** aber **fortlaufend**.
Wenn man sich den Index des letzten Elements merkt, kann einfach am Index + 1 das Element hinzugefügt werden.
**Zeitkomplexität**: $O(1)$
![[ArrayAdd.png]]

**Fall 2**
Daten liegen **sortiert und fortlaufend vor**.
Mittel [[Binäre Suche|binärer Suche]] wird die Einfügestelle gesucht und dann müssen alle Elemente rechts davon nachgerückt werden.

Zeitkomplexität: $O(\log n) + (O(n) \implies O(n)$
![[ArrayInsert.png]]

## Entfernen
**Fall 1**
Daten sind **nicht sortiert aber fortlaufend**.
Wir müssend das sequenziell durchsuchen und könnend dann das letzte Element an den freigewordenen Platz setzen.
**Zeitkomplexität:** $O(n) + O(1) \implies O(n)$
![[ArrayDelete.png]]

**Fall 2**
Daten sind sortiert und fortlaufend.
Die Stelle mittels [[Binäre Suche|binärer Suche]] gesucht und danach müssen alle Element nachgeschoben werden.
**Zeitkomplexität:** $O(\log n) + O(n) \implies O(n)$
![[ArrayDeleteSorted.png]]
## Bilanz
**Positiv**
- Effizient und schnell
- Direkter Zugriff, einfach
**Negativ**
- statisch -> konstanter Platzbedarf unabhängig vom Füllstand.
- Funktional limitiert
- Nicht kompatibel mit Generics.