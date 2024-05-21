RAM (Random Access Memory) ist ein [[Speicherzelle]] des Computers. Im RAM werden alle Daten gespeichert, welche der Computer momentan benötigt um zu funktionieren.

## SRAM = Static RAM
- 6 Transistoren pro Zelle
- Für Cache und Register im [[Mikroprozessor]]
- Hohe Geschwindigkeit
- Kleinere Speicherkapazität pro Chip

Wird für Register verwendent.

## DRAM = Dynamic RAM
- 1 Transistor pro Speicherzelle + einen Kondensator
- hohe Datendichte auf kleiner Chipfläche
- langsamer
- billiger
- muss alle **32** oder **64 ms** aufgefrischt werden

Werde für den Hauptspeicher benutzt.

### DRAM-Refresh
Der Kondensator in der Speicherzelle verliert langsam die elektrische Ladung. Damit verliert er den Speicherzustand.
Durch den Refreshcontroller DRAM-Controller werden die Kondensatoren alle **32** oder **64 ms** aufgefrischt, damit der Speicherzustand nicht verloren geht.
![[DRAM.png]]

## PSRAM = pseudo-statisches RAM
- DRAM mit eingebauter Auffrischung
- Auch: 1T-SRAM und cellularRAM