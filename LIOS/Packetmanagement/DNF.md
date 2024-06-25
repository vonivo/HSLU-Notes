DNF (Dandified Yum) ist ein Paketmanagement-System, das für [[RPM]]-basierte [[Linux]]-Systeme entwickelt wurde.

DNF ist eine "Erweiterung" von [[RPM]] und kann:
- Installationsquelle dynamisch auswählen.
- Unterstützt Plugins.
- Löst Abhängigkeiten auf.
=> Kompatibel mit YUM (Yellow Dog Updater)

# Befehle
- `dnf help`
- `dnf list` -> Installierte und verfügbare Pakete anzeigen.
- `dnf search KEYWORD` -> Pakete nach Keyword suchen.
- `dnf info PACKAGENAME`
- `dnf provides PATHNAME` -> Welches Paket passt zu Pfad
- `dnf install PACKAGENAME`
- `dnf update`
- `dnf remove` -> Entfernen inklusieve Dependencies, welche danach nicht mehr verwendet werden.

## Softwaregruppen
Bei Gruppen handelt es sich um Sammlungen von zusammengehörigen Paketen, die auf einmal installiert werden können.

Dabei existieren zwei Arten:

**Reguläre Gruppen** -> Sammlung von Paketen
**Umgebungsgruppen** -> Sammlung von regulären Gruppen.

**Bespiele**
- `dnf group list`
- `dnf goup list hidden`
- `dnf group info "Group Name"`
- `dnf group install "Group Name"

# Paket-Stream
In RedHat existieren "Application Streams" mit Profilen. Dadurch können verschieden Versionen von gleichen Softwarepaketen gleichzeitig installiert sein.

**Stream** -> Verschiedene Versionen
**Profil** -> Bestimmter Inhalt/Ausprägung

Installierbar sind immer **mehrere Streams** aber **nur ein Profil**.

**Beispiel:**
**Stream** -> perl in Version 5.24 und Version 5.26; python Version 2.X und Version 3.X

**Profil** -> "minimal", "common", "developer" bei z.B. Java.

## Befehle
- `dnf module list` -> Verfügbar Module auflisten
- `dnf module list module-name` -> Modulstreams für bestimmtes Modul auflisten.
- `dnf module info module-name`
- `dnf module provide package` -> Zeigt an, welches Modul ein bestimmtes Paket zu Verfügung stellt.
- `dnf module install name:stream/profile` -> Stream und Profile optional

# History
Alle Transaktionen, welche mit DNF ausgeführt werden, sind in der Datei `/var/log/dnf.rpm.log` festgehalten.

`dnf history` -> Anzeigen der History
`dnf history undo <Number>` -> Eine bestimmte Transaktion umkehren.


# Repositorys
All Repos auflisten:
`dnf repolist all`

Repos aktivieren/deaktivieren:
`dnf config-manager --enable <repo>`

Repo hinzufügen:
`dnf config-manager --add-repo="url"` -> `.rpo`-Datei wird in `/etc/yum.repos.d` hinzugefügt.