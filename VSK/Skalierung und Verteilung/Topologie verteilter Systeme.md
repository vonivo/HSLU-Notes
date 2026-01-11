## Embedded
Die Embedded-Topologie ist für Systeme wo asynchrone Ausführung von Task oder Hochleistungs-Computing gefragt sind.

![[EmbeddedTopology.png]]
Jeder Knoten enthält dabei sowohl die Daten als auch das Programm.
Die Kommunikation findet über **TCP/IP** statt.


## Client / Server
Die Client-Server-Topologie ist für Server-Knoten welche erstellt und skaliert werden können.
Clients kommunizieren mit diesen Knoten, um auf Daten zuzugreifen.

Die Daten und die Applikation sind dabei **getrennt.**
![[ClientServer.png]]
**Client-Arten**
- Native Client
- MemCache-Client
- [[Representational State Transfer (REST)|REST]]-Client
- etc.