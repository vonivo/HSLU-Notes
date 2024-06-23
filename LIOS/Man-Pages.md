Um als Benutzer einem bestimmten [[Prompt|Befehl]] zu finden und dazu auch Hilfe zu erhalten, existieren die sogenannten Handbuchseiten (man pages).

*Man pages* liegen bei Sofwarepaketen bei, für die sie Dokumentation bereitstellen und können über die das [[Terminal]] mit dem [[Prompt|Befehl]] `man` aufgerufen werden.

*Man pages* sind in weiten Teilen ausdrücklich nicht durch den POSIX-Standard standardisiert, sondern nur auf das Minimus standardisiert.

*Man pages* befinden sich unter `/usr/share/man` in einer festgelegten Verzeichnis-Hierarchie.


# Apropos
Mit dem Befehl `apropos` (oft ein Wrapper oder Alias für `man -k`) sucht in der **Whatis-Datenbank** nach Stickwörtern. Als Antwort enthält man eine Liste der gefundenen Einträge samt Section-Nummern.

Dieser Befehl kann gut verwendet werden, um nach einem Bestimmten Befehl zu suchen.

Die **Whatis-Datenbank** muss nach einer Neuistallation zunächst mit `mandb -c` erstellt werden.

# Wahtis
Der Befehlt `whatis` zeigt eine Kurzfassung der Handbuchseite des Befehls an.

# Sections
Hanbücher in [[Linux]] sind in folgende acht Sections unterteilt, wobei der Standardabschnitt 1 ist:
1. Ausführbare Programme oder Befehle
2. Systemaufrufe (vom Kernel vorgegebenen Funktionen)
3. Bibliotheksaufrufe (von der Bibliothek bereitgestellte Funktionen)
4. Spezielle Dateien (normalerweise in [[Dateisystem#`/dev`|`/dev` ]])
5. Dateiformate und Konventionen (Konfigurationsdateien wie `/etc/passwd`)
6. Spiele
7. Sonstiges (z.B. man selbst)
8. Systemverwaltungsbefehle (normalerweise nur für root zugänglich)
9. Kernel-Routinen

Beispiel:
```bash
[labstuden@lios-1]$ man 5 passwd
```

