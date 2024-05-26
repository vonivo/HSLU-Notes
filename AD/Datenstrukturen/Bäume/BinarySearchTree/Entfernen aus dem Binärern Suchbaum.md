Das Entfernen aus dem [[Binärer Suchbaum|binären Suchbaum]] ist nicht so trivial wie es scheint.
Zuerst muss das zu entfernende Element mittels der [[Suche im Binärern Suchbaum|Suche]] gefunden werden, danach können 3 Szenarien entstehen:
- Das Element ist ein **Blatt** und hat **keine** Kinder
- Das Element ist ein **innerer Knoten** mit **einem** Kind
- Das Element ist ein **innerer Knoten** mit **zwei** Kindern

## Entfernen eines Blattes
Dieser Fall ist der Einfachste. Das Blatt wird einfach entfernt, der Baum behält seine Struktur und alle formalen Kriterien sind erfüllt.
![[BinarySearchTree_remove_leaf.png]]
## Entfernen Knoten mit einem Kind
Beim Entfernen eines Knoten mit **einem Kind-Knoten** (auch inklusive allfälligem Teilbaum) ist das Entfernen auch relativ einfach.
- Durch die Struktur sind alle Knoten im linken oder rechten Teilbaum kleiner/grösser  als der zu entfernende Knoten.

Daher kann der Knoten gelöscht werden und der **einzige Kind-Knoten** übernimmt den Platz.
![[BinarySearchTree_remove_one_child.png]]

## Entfernen Knoten mit zwei Kindern
Wenn ein Knoten zwei Kinder hat und entfernt werden soll, kann nicht einfach der rechte oder linke Knoten nachrückten, da ansonsten die formalen Regeln des Baumes verletzt werden.

In diesem Beispiel wird das Element 3 entfernt:
![[BinarySearchTree_remove_tow_children.png]]Die Lösung, man ersetzt das gelöschte Element mit Knoten am weitesten links (rechts) aus dem rechten(linken) Teilbaum. Dieser Knoten hat somit den kleinsten/grössten Wert im Teilbaum.

![[BinarySearchTree_remove_two_children_solution.png]]