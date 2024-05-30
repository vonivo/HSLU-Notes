Auch beim Entfernen aus einer [[Hashtabelle]] muss die [[Hashtabelle#Sondieren|Sondierungskette]] berücksichtigt werden.

## Fall 1
Aus dem folgendenden [[Array]] soll das Element `h` entfernt werden.

1. Suche nach Index 7 -> Treffer
 ![[Hastable_remove_search.png]]
 [[Komplexität]] für die Suche $O(1)$
 
2. Element entfernen
![[Hastable_remove.png]]
[[Komplexität]] für Entfernen $O(1)$

[[Komplexität]] Allgemein: $O(1) + O(1) \implies O(1)$

Diese Vorgehen funktioniert **im algemeinen nicht!!**, da eine Sondierungskette gebrochen werden kann.

## Sondierungskette
Das Element `o` mit dem Index 4 soll entfernt werden:
1. Das Element `o`wird an der Position 4 gefunden
![[HashTable_remove_collision.png]]
2. Element `o` wird entfernt.

$\implies$ Das Element `d`mit dem Index 3 wird nun nicht mehr gefunden, weil die Sondierungskette unterbrochen wurde.
![[HashTable_remove_broken_chain.png]]

### Problem
Ein leerer Array Platz zeigt  an, dass die Suche abgebrochen wird.

Wenn einfach das näcshte Element von Rechts nachrücken würde, kann es sein, dass dieses Element nicht zur Sondierungskette gehört und darum später auch nicht mehr gefunden werden kann.

$\implies$ Platz mit einem Platzhalter (**Tombstone**) füllen, welcher anzeigt, dass dort eine Sondierungskette ist.
![[Hashtable_remove_tombstone.png]]

>[!warning]
>Je mehr solcher **Tombstones** desto innefizienter wird die Suche.
>
>$\implies$ Alternative [[Hashtabelle mit Liste]]





