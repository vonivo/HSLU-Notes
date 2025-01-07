Ein RAID (Redundant Array of Independet Discs) ist eine redundante [[Storage|Speicher]]-Form.

## RAID 0
Der RAID 0 biete keine Redundanz und ist einfach eine Anhäufung von Discs die als eine angesprochen werden können.

R/W Schnell, da Operationen auf verschiedene Discs verteilt sind.
Ausfallwahrscheinlichkeit steigt.
![[Pasted image 20250105205723.png]]
## RAID 1
R schneller, da auf zwei Festplatten aufgeteilt wird.
Redundant, dafür 50 % zusätzlicher verbrauch.

![[Pasted image 20250105205730.png]]

## RAID 10
Kombination von R1 und R2
Ausfallsicherheit und Gewschwindigkeit steigen
![[Pasted image 20250105210026.png]]

## RAID 5
- Ein Teil des Diskplatzes wird für **Partity** reserviert.
- Parity über alle Disks verteilt, keine Engpässe beim Write.
- Bei Ausfall einer Festplatte können die Daten mit hilfe der anderen und der Parity wieder hergestellt werden.
- Min 3 Disks max ca. 10-12
- W langsamer, R schneller als eine HD.

## RAID 6
- 2 Parity-Platten auch verteilt.
- Doppeldiskausfälle abgedeckt