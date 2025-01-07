Um alle Prozessoren zu verbinden, muss ein Verbindungsnetzwerk gewählt werden. Dieses Netzwerk ist ein Trade off zwischen Geschwindigkeit und Kosten.

Diese Netzwerke können in zwei Kategorien klassifiziert werden.
- Topologie:
	- Wie sind die Prozessoren verbunden ?
	- Statisch oder dynamisch veränderbar?
- Routing
	- Wie werden Nachrichten verteilt (store and forward, wormhole, cut-through, circuit-switching, packet-switching)
	- Welcher Algorithmus zur Pfadbestimmung wird verwendet.

## Unidirektionaler Interconnect
![[Pasted image 20250107162340.png]]
## Lineares Feld
![[Pasted image 20250107162601.png]]
## Ring
- Symmetrisch
- Verbindungen könne uni-und Bidirektional sein.
- Integrierte Redundanz

## Stern
![[Pasted image 20250107162840.png]]
- Asymmetrisch
- SPOF

## Baum
![[Pasted image 20250107162936.png]]
- Asymmetrisch

## Koppelnetzwerk
![[Pasted image 20250107163023.png]]
- Geschaltetes Netzwerk oder Schaltnetz

## Hybercube
![[Pasted image 20250107163152.png]]
## Crossbar-Switch
![[Pasted image 20250107163242.png]]
- Jeder Punkt ist über eine bestimmte Anzahl Hops mit jedem anderen Punkt verbunden.
- Switches sind nicht blockierend

## Omega Netzwerk
![[Pasted image 20250107163522.png]]
- Weniger Komplex
- Switches blockieren