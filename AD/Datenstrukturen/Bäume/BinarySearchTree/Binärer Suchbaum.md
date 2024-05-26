>[!info]
>Ein binärer Suchbaum (binary search tree) ist im Wesentlichen identisch mit einem [[Binäre Bäume|binären Baum]]. Sie besitzen auch die [[Ordnung eines Baumes|Ordnung]] 2.
>
>Als Erweiterung enthalten Sie aber neben dem eigentlichen Datenelement noch einen Schlüsselwert, nach welchem die Elemente im Baum geordnet werden, dies ermöglicht dann die effiziente Suche.

Der Schlüssel kann aus (Teil-)Daten des Datenelements bestehen. (z.B. Matrikelnummer eines Studenten) oder auch aus (Teil-)Daten berechnet werden (z. B. [[Equals & Hashcode#Hashcode|hashCode()]]).

## Geordneter binärer Suchbaum
Beim einem binären Suchbaum gelten folgende Regeln:
- Jeder Schlüssel im **linken** Teilbaum ist **kleiner** als der Schlüssel im Knoten selbst.
- Jeder Schlüssel im **rechten** Teilbaum ist **grösser** (oder gleich) dem Schlüssel im Knoten selbst.

![[BinarySearchTree.png]]

Dadurch wird die effiziente [[Binäre Suche]] ermöglicht.

## Operationen
- [[Suche im Binärern Suchbaum|Suche]]
- [[Einfügen in den Binärern Suchbaum|Einfügen]]
-  [[Entfernen aus dem Binärern Suchbaum|Entfernen]]
- [[Balancieren von binären Bäumen|Balancieren]]