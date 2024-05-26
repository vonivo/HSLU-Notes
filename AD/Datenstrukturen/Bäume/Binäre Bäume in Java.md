Java kennt verschiedene Implementationen, welche auf [[Bäume|Bäumen]] basieren.
## `TreeSet<E>`
- Implementiert ein navigierbares `SortedSet<E>`.
- `Set`-Semantik: Keine Duplikate erlaubt.
- Sorted: Das `Set` kann mit einem `Iterator` in sortierter Reihenfolge durchlaufen werden ([[Inorder|Inorder-Traversierung]])
- Nutezn das [[compareTo & Comparable|Comparable<T> bzw. Comparator<T>]]-Interface

## `TreeMap<K,V>`
Datenstruktur mit `Map`-Semantik, welche die Keys auch als `Set` zur schnellen Suche in einem Baum speichert.

## Red-Black-Baum
- Spezielle Implementation, die einen Kompromiss zwischen reduziertem Aufwand für das [[Balancieren von binären Bäumen|Balancieren]] und einer trotzdem noch schnellen Suche macht.
	- Knoten werden dabei nach dedizierten Regeln "rot" und "schwarz" eingefärbt. (Zusätzliches Attribut notwendig.)
	- Auf den Pfäden sind Regeln zur Reihenfolge und Anzahl der Farben der Knoten definiert. Werden die Regeln verletzt, ist eine "Reparatur" des Baumes notwendig.
- Effekt: Der Baum ist zwar nicht in jedem Fall auf ein Minimum an Ebenen ausbalanciert, aber der Aufwand für die Suche ist trotzdem garantiert mit $O(\log n)$

