# UMA
Bei der Unified Memory Architektur besitzt jede CPU direkten Zugriff auf alle Speicherstellen.

**Vorteile**
- Einfacher und schneller Kommunikationsmechanismus
**Nachteile**
- Wenige Adressräume
![[Pasted image 20250106192542.png]]
## NUMA
Bei der Shared Memory Architektur werden 2 oder mehrere [[Symmetric Multiprocessing|SMPs]] miteinander verbunden.
- Ein Globaler Adressraum
- Ein SMP kann auf das Memory jedes anderen zugreifen.
- Nicht alle Prozessoren haben dieselbe Zugriffszeit.
![[Pasted image 20250106192549.png]]

## Vergleich Anzahl Prozessoren
Mit steigender Anzahl Cores wird beim Kommunikationsmodell das Nachrichtenmodell und bei der physischen Verbindungen das Netzwerkmodell bevorzugt:
![[Pasted image 20250106193102.png]]