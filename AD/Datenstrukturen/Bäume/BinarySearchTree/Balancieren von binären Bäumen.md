Damit die maximale Perfomance bei der Suche gewährleistet werden kann, sollte ein Baum im Verhältnis zu seinem [[Gewicht eines Baumes|Gewicht]] eine möglichst **minimale** Anzahl an [[Baum Niveaus|Niveaus]] haben.
$\implies$ Daraus entstehen kürzere Pfäde.

Dieser Zustand lässt sich wie folgt definieren:
Ein Baum gilt als **ausgeglichen**, wenn sich die **Höhen** des linke und rechten Teilbaums um maximal **1 Niveau** unterscheiden. (Dieser Zustand kann sich bei jedem [[Einfügen in den Binärern Suchbaum|Einfügen]] und [[Entfernen aus dem Binärern Suchbaum|Entfernen]] ändern.)

Um den Baum wieder auszugleichen existieren [[Algorithmus|Algorithmen]]. Diese Algorithmen **balancieren** den Baum.


## Beispiel
Der Baum ist unausgeglichen, da sich die Niveaus um 2 unterschieden.
![[BinarySearchTree_unbalanced.png]]Der Baum kann durch eine **einfache Rotation** nach rechts ausgeglichen werden.
![[BinarySearchTree_rotation.png]]Die Knoten **d** und **f** "rotieren". Dabei wird der **rechte Teilbaum** (e) von Knoten **d** neu zum **linken Teilbaum** von **f**. (Äquivalent wäre eine Rotation nach links. (Baum gespiegelt)).


Soll ein binärer Suchbaum ständig ausgeglichen sein, muss nach jedem Einfügen/Entfernen die Höhendifferenz überprüft werden und gegebenenfalls durch Rotationen ausbalanciert werden.

Das macht die Operationen aufwändiger, sie behalten jedoch die Ordnung von $O(n)$.

Die Suche nach einem Kompromiss hat zur Entwicklung von verschiedenen Spezialformen geführt:
- AVL-Baum
- Red-Black-Baum