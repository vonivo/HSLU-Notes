Ein einzelner [[Switch]] wird nicht reichen, um das gesamte [[Netzwerk]] in einem [[Rechenzentrum]] aufzubauen.

Darum existierten diese 3 Ebenen:
![[Pasted image 20250104103931.png]]
## Leaf / Access
In der Leaf/Access-Ebene ist die unterste Ebene der LAN-Struktur.
Die Leaf-Ebene dient dazu, um:
- Server anzuschliessen,
- Peripherie anzuschliessen,
- Abgänge auf Gebäude Land.

## Backbone / Spine
Diese Ebene bildet das Rückgrat des zentralen Netzwerks.
Es ist für die Verbindungen innerhalb des RZ zuständig.

## Peering / Pheripherie
Diese Schicht stellt den Anschluss nach aussen sicher, sie ist ausserdem zentraler Knoten für [[Firewall|Firewalls]] und [[ITEO/Rechnezentrum/Netzwerk/Router|Routers]].

## Aggregation Layer
Ist das RZ grösser, kann zusätzlich noch der Aggregationlayer ergänzt werden, dieser ist für die direkten Verbindungen der Serverfarms zuständig. Auch ermöglicht er die Verbindung innerhalb von Rackreihen.
![[Pasted image 20250104104559.png]]
**Beachte**
- Nicht nur Topdown-Verbindungen.
- Netzwerkloops beachten.
- Wege kurzhalten.

## Beispiel Facebook
Server-Pods mit jeweils 
- 24 Racks und 2 [[RZ Lan Topologie#TOR|TOR]] [[Switch|Switches]]
- 4 Fabric-Switches welche alle TOR-Switches verbinden.
![[Pasted image 20250104104848.png]]
Eigenschaften:
- High Performance Netzwerk
- Hoher Datenverkehr
- Einfache Erweiterbarkeit
- Hohe Redundanz.

Auch im Aggreation-Layer hohe Redundanz:
- Server-Pods werden kreuzweise mit Spine-Planes verbunden.
- Spine-Planes besitzen wiederum 4-Spine-Switches.
- Diese Spine-Switches sind dann wiederum mit 4 Edge-Switches verbunden

![[Pasted image 20250104105322.png]]