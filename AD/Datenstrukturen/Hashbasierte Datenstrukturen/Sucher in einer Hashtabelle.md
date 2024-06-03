Beim Suchen in einer [[Hashtabelle]] muss berücksichtigt werden, dass das gesuchte Element nicht zwingend an dem berechneten Index liegt, sondern durch das [[Hashtabelle#Sondieren|Sondierenn]] weiter rechts liegen kann.

Dass heisst, ab dem berechneten Index muss in der Sondierungskette so weit nach rechts gesucht werden, bis **ein leerer Platz** auftaucht oder das Element **gefunden** wird.

### Beispiel
**Suche nach Element `h`**
Das Elemnt `h` hat den Index 7. Die Suche ist ein Treffer:
![[HashTabe_search.png]]
[[AD/Algorithmen/Komplexität]]: $O(1)$

**Suche nach Element `a`**
Das Element `a` hat den Index 0. Die Suche ergibt ein leeres Feld -> kein Treffer:
![[HashTable_search_nonmatch.png]]
[[AD/Algorithmen/Komplexität]]: $O(1)$

**Suche nach Element `d`**
Das Element `d` hat den Index 3. Am Index 3 ist jedoch das Element `x`-> Kollision. Nun wird rechts von `x`weitergesucht.
![[HashTable_search_collision.png]]
Es wird rechts von 3 weitergesucht:
1. Element `o` -> Kein Treffer.
2. Element `d`-> Treffer.
3. Bei Index 6 hätte die Suche terminiert, weil kein Element vorhanden ist.
[[AD/Algorithmen/Komplexität]]: $O(n)$

**Suche nach Element `e`**
Das Element `e` hat den Index 4. Am Index 3 ist jedoch das Element `o`-> Kollision. Nun wird rechts von `o` weitergesucht.
![[HashTable_search_collision_nonmatch.png]]
Es wird rechts von 4 weitergesucht:
1. Element `d` -> Kein Treffer.
2. Index 6 leer -> kein Treffer, Suche terminiert da Platz leer ist.
[[AD/Algorithmen/Komplexität]]: $O(3)$