Eine [[Klasse]], welche [[Vererbung|vererbbar]] ist, muss jede Nutzung von überschreibbaren Methoden dokumentieren. Das heisst, es muss dokumentiert werden, wann welche Methoden wie aufgerufen werden.

**Beispiel**
Die [[Methode]] `AbstractCollection.remove(Object o)`:
```
Removes a single instance of the specified element from this collection, if it is present (optional operation). More formally, removes an element `e` such that `Objects.equals(o, e)`, if this collection contains one or more such elements. Returns `true` if this collection contained the specified element (or equivalently, if this collection changed as a result of the call).

Implementation Requirements: This implementation iterates over the collection looking for the specified element. If it finds the element, it removes the element from the collection using the iterator’s `remove` method. Note that this implementation throws an `UnsupportedOperationException` if the iterator returned by this collection’s `iterator` method does not implement the `remove` method and this collection contains the specified object.
```
Diese Beschreibung unter **Implementation Requirements** zeigt an, dass das Überschreiben von `iterator.remove()` Auswirkungen auf diese [[Methode]] hat.

Klassen welche vererbt werden, müssen nicht nur dokumentieren, sondern teilweise auch genau gewählte `internals` (Methoden oder Attribute) über `protected` zur Verfügung stellen.

Damit herausgefunden werden kann was `protected` sein soll, sollte **etwa** 3 **Subklassen** geschrieben werden. (Am bestem von anderen Entwicklern) Danach kann entschieden werden was `protected` ist und was `private`.

>[!warning]
>Im [[Konstruktor]] einer Superklasse darf keine [[Methode]] aufgerufen werden, welche überschreibbar ist, da Subklassen erst nach der Superklasse initialisiert werden.

Wenn eine [[Klasse]] nicht explizit auf [[Vererbung]] ausgelegt ist, sollte sie nicht vererbbar sein. Da sich ansonsten mit Änderungen an dieser [[Klasse]] Bugs in potenziellen Subklassen einschleichen könnten.

>[!info]
>Wenn eine [[Klasse]] selbst keine überschreibbaren Methoden aufruft, ist sie sicher für die [[Vererbung]]. Dies kann über eine `private` Helper Methode gemacht werden, welche dann von einer `overridable`-Wrapper-Methode aufgerufen wird.

