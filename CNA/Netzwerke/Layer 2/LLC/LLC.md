Die Protokolle [[IEEE-802]] bieten bis zur [[MAC]]-Schicht nur einen Best-Effort-Diesnt. Sprich ein Frame wird so gut es geht übertragen und Frameverluste werden nicht erkannt.

Da schafft LLC Abhilfe.
-> In jedem Frame wird eine LLC-Header eingefügt.
-> Header enthält Folge- und Bestätigungsnummer.


LLC bietet insgesammt drei Dienste:
- Unzuverlässigen Datagramdienst -> Werbesendung, normaler Brief
- Bestätigter Datagramdienst -> eingeschriebener Brief mit Rückantwort
- Zuverlässiger, verbindungsorientierter Dienst -> dedizierter Verbindungskanal, Rohrpost, Botenübermittlung.

