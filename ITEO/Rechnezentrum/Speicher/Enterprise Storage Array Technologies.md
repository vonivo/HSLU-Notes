Ein [[Storage-Systeme#Storage Array (EVA)|Storage Array]] kann mit zwei Technologien umgesetzt werden:

## Conventional
- Disks werden zu Arrays mit passendem [[RAID]]-Level zusammengestellt.
- Bereitstellung von LUNs aus Teilen von physikalischen Arrays (fixe Plattenzuteilung zu LUN/Server) -> ungeliche Auslastung
![[Pasted image 20250106190654.png]]
## Compellant
- Disks werden zusammengefasst und als Gesamt-Block-Array verwaltet.
- Zusammenstellung der virtuellen Disks via Lokale Intelligenz.
- Blöcke über das gesamte Array verteilt.
- RAID Level wird innerhalb der Auswahl gewährleistet
- Gleiche Zugriffszeiten für alle
![[Pasted image 20250106191039.png]]