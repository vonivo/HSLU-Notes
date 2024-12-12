Es gibt verschiedene Arten von Links zwischen Dateien. 

- [[Konkrete Betriebssysteme#UNIX|UNIX]] verwendet Hard und Softlinks
- [[Konkrete Dateisysteme|NTFS]] verwendet Hadlinks, Junctions und Symbolic Links

# Hardlinks
Mehrere Dateinamen verweisen auf einen I-Node.

![[Pasted image 20240530110656.png]]
# Junction
Werden nur für Verzeichnisse verwendet. Hier kann dann mit einem anderen Pfad auf das verlinkte Verzeichnis zugegriffen werden.

# Softlink
Der Softlink (Symbolic Link) legt ein Pseudofile an mit dem Pfadnamen der verlinkten Datei. 
- Grösserer Aufwand als Hardlinks, weil der ganze Pfad verfolgt werden musse
- Wird das fremde File gelöscht funktioniert der Link nicht mehr

![[Pasted image 20240530110630.png]]