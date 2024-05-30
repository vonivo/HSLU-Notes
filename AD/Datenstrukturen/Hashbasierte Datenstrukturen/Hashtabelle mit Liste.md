Die Hashtabelle mittels einer [[Liste]] ist eine Optimierung zu einer Klassischen [[Hashtabelle]] welche über ein [[Array]] implementiert wird.
Sie löst das Problem der [[Hashtabelle#Sondieren|Sondierung]] mittels einer zweiten Dimension und einer weiteren [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]].

- Elemente werden nicht mehr direkt in einem Array abgelegt, sondern in einer Liste innerhalb des Arrays.
![[Hashtable_linkedlist.png]]
- Bei einer Kollision wird nun einfach die Liste erweitert


## Vorteile
- Sehr einfacher Umgang mit Kollisionen
- Listen werden sequenzielle durchsucht -> Kollisionen wirken sich nur lokal aus
- Aufwand für das Einfügen ist immer $O(1)$ durch die Liste.

## Nachteile
- Mehr Speicherplatz benötigt, da noch ein Node-Objekt gebraucht wird.