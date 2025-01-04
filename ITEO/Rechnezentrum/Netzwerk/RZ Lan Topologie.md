Die [[Netzwerk]]-Topologie im [[Rechenzentrum]] kann mit zwei verschiedenen Formen umgesetzt werden:
- TOR
- EOR

## TOR vs EOR

| Kriterium         | TOR                   | EOR                         |
| ----------------- | --------------------- | --------------------------- |
| Kabelmanagement   | Einfacher             | Komplexer                   |
| Switch-Anzahl     | Viele kleine Switches | Weniger, grössere Switches  |
| Kosten (Hardware) | Höher (mehr Switches) | kleiner, (weniger Switches) |
| Skalierbarkeit    | Einfach               | Komplexer                   |
| Latenz            | Geringer              | Etwas höher                 |
| Verwaltung        | Komplexer             | Einfacher                   |

## TOR
Jedes Rack besitzt eigene Switches.
![[Pasted image 20250104093012.png]]

## EOR
Pro Rack-Reihe existiert ein **Switch-Rack**
![[Pasted image 20250104093107.png]]



