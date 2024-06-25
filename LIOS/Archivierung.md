Die Archivierung von Komprimierung von Daten ist nützlich bei Datensicherungen und um Daten zu übertragen.

**Tar** ist ein sehr verbreitetes und auch altes Tool, um solche Archive zu erstellen.
**Tar** bedeutet *Tape ArchiveR*
- Ein Tar-Archiv ist eine strukturierte Folge von Dateien mit Metadaten und Index zu jeder Datei. (Somit können einzelne Dateien extrahiert werden.)
- Tar ermöglicht das Speichern auf mehreren aufeinanderfolgenden Medien
- Tar kann mithilfe von `gzip`, `bzip2` oder `xz` komprimiert werden

**Beispiel**
```bash
[root@lios ~]# tar -cf /root/etc.tar /etc
```
```bash
[root@lios ~]# tar -tf /root/etc.tar
etc/
etc/fstab
etc/crypttab
etc/mtab
...optupt omitted...
```

# Optionen

| Option                       | Beschreibung                                                                                                                                |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `-c, --create`               | Neues Archiv erstellen                                                                                                                      |
| `-x, --extract`              | Aus vorhandenem Archiv extrahieren                                                                                                          |
| `-t, --list`                 | Inhaltsverzeichnis eines Archivs auflisten                                                                                                  |
| `-v, --verbose`              | Zeigt welche Dateien archiviert oder extrahiert werden                                                                                      |
| `-f, --file`                 | Filename. Auf diese Option muss der Dateiname des zu verwendenden oder zu erstellenden Archivs folgen                                       |
| `-p, --preserve-permissions` | Berechtigungen für Dateien und Verzeichnisse beim Extrahieren eines Archivs beibehalten, **ohne die Aufhebung der Maskierung** zu entfernen |
| `-z, --gzip`                 | Komprimierug `gzip`(.tar.gz)                                                                                                                |
| `-j, --bzip2`                | Komprimierung `bzip2` (.tar.bz2) -> Bessere Komprimierung als `gzip`.                                                                       |
| `-J, --xz`                   | Komprimierung `xz`(.tar.xz) -> Bessere Komprimierung als `bzip2`.                                                                           |

