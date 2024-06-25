Das Linuxdateisystem ist wie ein [[Bäume|Baum]] aufgebaut. Der einzige Eintrittspunkt um auf das Dateisystem zuzugreifen ist über `/`. 
![[Linux_Dateisystem.png]]

Um auf eine Datei zugreifen zu können muss ein Pfad verwendet werden.
## Absoluter Pfad
Ein absoluter Pfad ist ein Pfad, welcher jedes Verzeichnis ausgehend von `/` enthält, bis das gewünschte File gefunden ist.
Zum Beispiel: `/home/labstudent/file1.txt`.

## Relativer Pfad
Ein relativer Pfad besitzt als Ausgangspunkt das aktuelle Verzeichnis welches mit `./` aufgerufen wird oder das vorherige Verzeichnis, welches mit `../` aufgerufen wird.

Beispiel:
Ausgansort: `/home/labadmin`
Ziel: `../labstudent/file1.txt`


## Wichtige Verzeichnisse
### `/boot`
Das boot-Verzeichnis enthält alle relevanten Dateien welche zum Starten und für den Bootvorgang nötig sind.

### `/bin`
Das Verzeichnis `/bin` ist ein [[UNIX-Links|Link]] auf das Verzeichnis `/usr/bin`.

### `/dev` 
Enthält spezielle Dateien welche für den Zugriff auf Hardwaregeräte benötigt werden. (dev kommt von Device)

### `/etc`
Verzeichniss in welchem alle Konfigurationsdateien gespeichert werden. (etc -> editable text configuration)

### `/home`
Unter dem Home-Verzeichnis speicher Benutzer ihre Dateien und Files.

### `/root`
Das Root-Verzeichnis ist das Home-Verzeichnis für den Superuser `root`.

### `/run`
Im Run-Verzeichnis werden alle Laufzeitdaten von Prozessen und Programme seit gespeichert. (Prozess-ID-Files, Prozess-Lock-Files, etc.)
Das Run-Verzeichnis wird bei jedem Neustart frisch erstellt.

### `/sbin`
Dieses Verzeichnis ist ein Link auf das Verzeichnis `/usr/sbin`.

### `/tmp`
Dieses Verzeichnis ist ein systemweiter beschreibbarer Speicherplatz für temporäre Dateien. Wenn Dateien länger als 10 Tag nicht aufgerufen, geändert oder modifiziert werden, werden sie gelöscht.

Es existiert noch ein weiteres temporäres Verzeichnis `/var/tmp` in diesem Beträgt der Threshold 30 Tage.

### `/usr`
In diesem Verzeichnis wird software installiert und gemeinsame genutzte Bibliotheken abgelegt, es beinhaltet auch schreibgeschützte Programmdaten.

Diese Verzeichnisse enthält folgende Verzeichnisse:
- **`/usr/bin`** -> Benutzer Commands für die Befehlszeile
- **`/usr/sbin`**-> Systemverwaltung-Kommando für die Befehlszeile als Supernutzer root, beispielsweise `shutdown`.
- **`/usr/local`** -> Lokal angepasst Software.

### `/var`
Dieses Verzeichnis enthält alle variablen Daten welche zwischen allen Bootvorgängen erhalten bleiben sollen. Dies kann unter anderem eine Datenbank sein, Cache-Verzeichnisse, Protokolldateien, etc.


## Dateisystembefehle

| Befehl    | Beschreibung                                                                     |
| --------- | -------------------------------------------------------------------------------- |
| `whomai`  | Zeigt den aktuellen Benutzer an.                                                 |
| `date`    | Gibt das aktuelle Datum aus (`date +%R` -> Nur Uhrzeit, `date +%x` -> nur Datum) |
| `file`    | Gibt den Typen einer Datein an                                                   |
| `cat`     | Ausgabe des Inhalts eines Files in der Konsole.                                  |
| `head`    | Gibt ersten paar Zeilen einer Datei aus.                                         |
| `wc`      | Wordcount, Kan Zeilen, Wörter, etc. einer Datei zählen.                          |
| `ls`      | Listet inhalt eines Verzeichnises auf                                            |
| `history` | Zeigt die Befehlshistory auf                                                     |

