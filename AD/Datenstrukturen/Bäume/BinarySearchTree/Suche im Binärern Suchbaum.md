Die Suche im Binären Suchbaum wird wie bei der [[Binäre Suche|binären Suche]] sukzessive halbiert, biss das Element gefunden wurde, oder man eine leere Menge hat.

## Beispiel
Suche nach dem Element 3
1. $3\lt4 \implies$ Linker Teilbaum
2. $3\gt 2 \implies$ Rechter Teilbaum
3. $3=3 \implies$ Element gefunden.

![[BinarySearchTree_search.png]]

Der [[Komplexität|Aufwand]] für die Suche beträgt somit $O(\log n)$ unter der Bedingung, dass der Baum balanciert ist.