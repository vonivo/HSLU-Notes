
# Cache-Speicher
Ein Cache-Speicher ist ein zwischen Speicher welcher zwischen [[Rechner|CPU]] und [[RAM]] eingesetzt wird. Er verbessert die Geschwindigkeit der Maschinen extrem. Dabei können verschieden Layers von Cache existieren.
![[Cache.png]]
## Eigenschaften
- Verringerung der Zugriffszeit
- Caching-Strategie notwendig
- Physikalisch verbaut


## Speicherhierarchie

| Typische Zugriffszeit | Anwendung (Technologie)                                                                                                                 | Typische Kapazität     |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| < 1ns                 | Register ([[RAM#SRAM = Static RAM\|SRAM]])                                                                                              | einige Bytes bis kByte |
| 2ns                   | Cache ([[RAM#SRAM = Static RAM\|SRAM]])                                                                                                 | 0.5 - 256 MB           |
| 5-10 ns               | Arbeitspeicher ([[RAM#DRAM = Dynamic RAM\|DRAM]])                                                                                       | 4-384 GB               |
| 3-10 ms               | Datenspeicher ([[Speichertechnologien#Halbleiterspeicher / Solid-State-Speicher\|SSD]] und [[Speichertechnologien#Magnetspeicher\|HD]]) | 50 GB - 30 TB          |
| 1- 110s               | Archiv, Backup, ext. Datenträger                                                                                                        | HD: bis 22TB           |
Datenhaltung: SSD/HD 10- 30 Jahre.
Tape: > 30 Jahre
Optisch: unklar 5-30 Jahre


## Organisation
Typischerweise wird pro Speicherzugriff nicht nur eine [[Speicherzelle]] abgefragt, da dies viel zu ineffizient wäre.
Im Normalfall werden **4/8 Speicherzellen angesprochen**. Daraus resultiert eine typische Busbreit von 4 * 8=32 oder von 8 * 8=64 Bit.
![[StorageOrganisation.png]]