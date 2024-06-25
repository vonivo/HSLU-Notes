Der **RedHat Package Manager** ist der Packagemanager welcher unter Red Hat verwendet wird.

>[!info]
>Das Ziel von RPM ist, ein [[Archivierung|archiv]] zur Softwareinstallation und -aktualisierung sowie kryptografische Sicherheit, automatische Scripte, [[Man-Pages]] und Binärdateien bereitzustellen.

# Paketname
Der Name eines RPM Pakets besteht aus vier Teilen:
`Coreutils-8.32-31el9.x86_64.rmp`
1. Name: `Coreutils` -> Beschreibt Inhalt.
2. Version: `8.32` -> Versionsnummer der Software.
3. Release: `31.el9` -> Releasenummer des Pakets auf Grundlage der Version. (Wird durch den Verpackenden festgelegt.)
4. Architektur: `x_86_64` -> [[Von-Neuman-Architektur|Prozessorarchitektur]]

# Repositorys
Softwarepakete werden meist aus einem Software-Repository heruntergeladen und installiert. Für die Installation wird nur der Name benötigt.

Befinden sicher mehrere Versionen desselben Pakets im Repo wird die neuste Version installiert.

# Befehle
RPM verwendet für Abfragen fast immer die lokale Datenbank der installierten Pakete.

>[!error] Achtung
>Soll anstatt der lokalen DB ein extern heruntergeladenes Paket (`.rpm`-Datei) abgefragt werden, muss der Parameter `-p filename.rpm` verwendet werden.

## Abfragen
- `rpm -qa` -> Alle installierten Pakete auflisten
- `rpm -qf FILENAME` -> Ermitteln, welches Paket FILENAME bereitstellt.
- `rpm -q PAKET` -> Installierte Paketversion anzeigen.
- `rpm -qi PAKET` -> Detaillierte Informationen zu Paket.
- `rmp -ql PAKET` -> Auflisten der installierten Dateien durch Paket.
- etc.

## Installieren
`rpm -ivh fileNameToPackage-4.0.1-6el9.x86_64.rpm`
- `-i` -> install
- `-v` -> verbose (Informationen zum Installationsvorgang)
- `-h` -> Ladebalken durch `#`.

# `rpm2cpio`
Das Tool `rpm2cpio` wird dazu verwendet, um Dateien eines Pakets zu extrahieren, ohne das Paket zu installieren.
Das Programm konvertiert `rpm`-Archiv in ein `cpio`-Archiv.

Wenn das Archiv konvertiert wurde, kann mit `cpio` Dateien extrahiert werden.

`rpm2cpio httpd-2.4.1-75el9.x86_64.rpm | cpio -idv`
