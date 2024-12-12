Jede Partition wird in Blöcke aufgeteilt .

Beim Formatieren wird die Blockgrösse festgelegt (2er Potenz).
- kleine Blockgrösse: gute Ausnutzung der Plattenkapazität (durchgezogene Linie)
- grosse Blockgrösse: schnellerer Datentransfer (gestrichelte Linie)

![[Pasted image 20240530101404.png]]

Es werden immer ganze Blöcke in den Festplattencache geladen/geschrieben

Abspeicherung soll so zusammenhängend wie möglich sein

Verwaltet werden die Blöcke durch das [[Dateisysteme|Dateisystem]] des [[Betriebssysteme|Betriebssystem]]
- Mithilfe von [[FAT]] oder [[I-Node-Verwaltung|I-Nodes]] und [[Dateien als verkettete Liste|verketteten Listen]]

Die Zugriffszeit wird von der Such-/Wartezeit bestimmt
- Aufgrund der Rotation und Lesekopf-Position