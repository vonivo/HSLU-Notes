FAT steht für File Allocation Table und ist ein [[Dateisysteme|Dateisystem]]

FAT ist folgendermassen aufgebaut:
- Tabelle innerhalb der Dateisystemstruktur der Partition mit fester Grösse
- Jeder Cluster ([[Blöcke|Zuordnungsblock]]) des Dateisystem wird mit einem Eintrag in der Tabelle festgehalten
	- Jeder Cluster hat einen Zustand: Frei, Beschädigt, Belegt
	- Ist der Status Belegt gibt es einen Link zum nächsten Cluster, oder ein -1 zum signalisieren dass das Ende der Datei erreicht wurde
	
![[Pasted image 20240530102911.png]]