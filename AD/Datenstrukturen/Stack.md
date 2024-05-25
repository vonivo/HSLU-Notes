Ein Stack ist eine **indirekte**, **geordnete** [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]], welche extrem viel Verwendet wird (vgl. [[Call-Stack]]).

Die Elemente sind als Stapel gespeichert und nach dem LIFO-Prinzipt organisiert (Last-In-First-Out).

Der Stack unterstützt meistens 3-[[Methode|Methoden]]:
- **push(E e)**-> fügt ein Element oben auf den Stapel hinzu.
- **E pop()** -> Entnimmt dem Stack das oberste Element
- **E peek()** -> Liefert das oberste Element zurück, jedoch ohne es zu entfernen.

## Operationen
### Array
Implementation mit einem [[Array]] (Index des letzten Elements wird gespeichert.)
- **push(E e)** $\implies O(1)$
- **E pop()** $\implies O(1)$
- **E peek()** $\implies O(1)$

- Grösse ist beschränkt
- Maximaler Platz ist immer belegt
- Schnell

## Liste
Implementation mit einer [[Liste]]. (Einfach verkette Liste reicht aus.)
- **push(E e)** $\implies O(1)$
- **E pop()** $\implies O(1)$
- **E peek()** $\implies O(1)$

- Leerer Stack benötig fast kein Platz
- Grösse dynamisch
- Speicheranforderung für neue Elemente notwendig, -> langsamer

## Java Klassen
![[Stack_JCF.png]]