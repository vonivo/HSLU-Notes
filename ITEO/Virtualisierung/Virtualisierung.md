Virtualisierung hat mehrere Vorteile:
- **Workload Isolation**: Isolieren von eignen Apps auf einem Server (z.B. bei einem Neustart muss nur die entsprechende VM neu gestartet werden und nicht der ganze Server)
- **Workload Consolidation**: VMs können auf einem Hypervisor zusammengefasst werden und so die HW besser ausnutzen.
- **Workload Migration**: Hypervisoren können geclustert werden und so VMs im laufenden Betrieb verschoben werden.
- **Workload Embedding**: Gleiche Arten von Workload können bei Bedarf hochgefahren werden. (Skalierung.)

## Herausforderung
- Applikationen und OS wissen nicht dass eine VM existiert und sie Resourcen teilen.
- VMM sollte den SW-Stack von Guest-OS gegenüber anderen Guests isolieren.
- Der VMM sollte ein Interface zu den Guest-OS bieten.