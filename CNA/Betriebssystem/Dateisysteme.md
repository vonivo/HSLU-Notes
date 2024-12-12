Das Dateisystem ist eine Struktur des [[Betriebssysteme|Betriebssystem]] um Files zu verwalten.

>Als **Files** werden Daten auf der Festplatte bezeichnet
>
>Für Langzeit Datenstorage gibt es drei essentielle Anforderungen:
>- Die Möglichkeit grosse Datenmenge abzuspeichern
	- Die Kapazität vom Memory ist durch die Grösse des [[Virtueller Speicher|virtuellen Speicher]] begrenzt. Für viele Anwendungen ist das nicht ausreichend. 
>- Persistenz
	- Daten im Memory sind nicht persistent, sie gehen verloren wenn ein Prozess endet
> - Paraleller Zugriff
	- Informationen im Adressraum eines Prozesses sind nur für den Prozess selbst verfügbar. Deshalb ist das keine Option für Daten welche mehrere [[Prozesse]] (gleichzeitig) brauchen

Das [[Betriebssysteme|Betriebssystem]] stellt über [[Systemaufrufe]] verschiedenste Dienste zur Verfügung: zur Benennung, Strukturierung, Typisierung, Zugriff, Schutz

Für ein Dateisystem müssen folgende Dinge festgelegt werden:
- Länge und erlaubte Zeichen der Namen
- interner Aufbau (unstrukturierte Byte Folge, Records)


## Typische Dateioperationen
> Create → Anlegen einer leeren Datei, Setzen von Attributen
> Delete → Freigabe des Platzes auf er Platte
> Open → Lesen der Attribute und Festplattenadressen
> Close → Löschen des internen Speichers für Verwaltungsinformationen
> Read → Lesen einer Anzahl Bytes ab der momentanen Position in bereitgestellten Puffer
> Write → Schreiben ab der momentanen Position
> Append → Schreiben am Ende
> Seek → Dateizeigerpositionierung
> Get/Set → Attributzugriff bzw. -änderung
> Rename → Namensänderung

## Typische Verzeichnisoperationen
> Create → Anlegen eines leeren Verzeichnisses
> Delete → Freigabe des Platzes auf der Platte (nur wenn leer)
> Opendir → Öffnen der Verzeichnisdatei
> Closedir → Löschen des internen Speichers
> Readdir → Lesen des nächsten Dateieintrags
> Rename → Namensänderung
> Link → Ezeugen eines symbolischen Dateieintrags auf eine Datei an anderer Stelle
> Unlink → Löschen eines Dateieintrages oder Verweises


# Filessystem Implementierung
- Eine Festplatte kann in eine oder mehrere Partitionen aufgeteilt werden

![[Pasted image 20240526214327.png]]

- Der Master Boot Record (MBR) wird verwendet um den Computer zu booten 
	- Das Ende des Master Boot Records enthält die Partitionstabelle 
	- Das [[BIOS]] führt den MBR aus und dieser selektiert den Boot Block der Aktiven Partition 
- Der Bootblock einer Partition lädt das Betriebssystem in der Partition
- Der Superblock enthält alle wichtigen Attribute eine

Jede Partition wird in [[Blöcke]] aufgeteilt. 

# Konkrete Dateisystem
Für eine Liste von konkreten Dateisystemen siehe: [[Konkrete Dateisysteme]]

# Konsistenz
Nach einem Systemzusammenbruch kann das Filesystem in einem inkonsistenten Zustand sein
- Vor allem wenn die [[Blöcke]] der Dateiverwaltung ([[Dateien als verkettete Liste]], [[I-Node-Verwaltung]]) nicht richtig geschrieben wurden.  

Konsistenztests erfolgt auf File- und Blockebene:
- Bestimmte [[Blöcke]] sind weder Files zugeordnet noch frei
- Ein Block tritt zweifach als frei auf
- Ein Block ist zwei verschiedenen Files zugeordnet

[[Defragmentierung]] ist hier ebenfalls wichtig.


# Dateiverlust
Um Dateiverlust zu vermeiden werden [[Backup|Backups]] eingesetzt