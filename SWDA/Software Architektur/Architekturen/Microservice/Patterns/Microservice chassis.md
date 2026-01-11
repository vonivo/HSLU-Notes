Um einen Microservice zu entwickeln, müssen viele Cross-Cutting-Concerns wie:
- Security
- Externe Konfiguration
- Logging
- Health-Check
- Metrics
- Distributed Tracings
- etc.
umgesetzt werden.

Dies bei jedem Service einzeln umzusetzen ist viel zu aufändig.

Um dieses Problem durchzuführen, gibt es zwei Varianten:
1. Service-Template (Funktioniert, entspricht aber eher dem Copy-Paste Ansatz)
	- Problem hierbei: Jeder Service muss danach einzeln angepasst werden.
- Service-Template mit Chassis:
![[Microservice-Chassis.png]]

Das Chassis beinhaltet dann:
- Wiederverwendbare Build-Logik
- Mechanismen für die Cross-Cutting-Concersn. Sprich es werden Dependencies zusammengeführt und Konfiguriert.