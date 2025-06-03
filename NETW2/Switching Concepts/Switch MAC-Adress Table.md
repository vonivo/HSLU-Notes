Ein Switch nutzt die **Ziel-MAC-Adresse**, um das [[Frame Forwarding|Egress-Interface]] zu bestimmen.

Die MAC-Adress-Table (oder Content Adressable Memory (CAM) Table) wird zur Laufzeit vom Switch erlernt.

Die Tabelle enthält eine Spalte für Zieladresse, Interface und Timeout.

| Destinationadress | Interface | Timout |
| ----------------- | --------- | ------ |
| EE                | 1         | 5min   |
| AA                | 2         | 2min   |
