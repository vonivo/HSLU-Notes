Durch Partitionierung kann eine physische Speichereinheit (z.B. SSD) in mehrere logische Speichereinheiten unterteilt werden.

Die Partitionierung ist in folgenden Fällen nützlich:
- Verfügbarer Speicherplatz für Anwendungen oder [[Nutzerverwaltung|Benuzter]] begrenzen.
- Betriebssystem und Programmdateien von den Benutzerdateien trennen.
- Separaten Bereich für Speicherauslagerung (Swap).
- Verwendung des Speicherplatzes begrenzen um die Leistung von Diagnosetools und Image-Backups zu steigern.

Die Grösse einer Partition wird in einer Partitionstabelle festgehalten.

# Master Boot Record (MBR)
**MBR** ist die traditionelle Partitionstabelle der älteren Betriebssysteme.
Der MBR ist immer zuvorderst auf dem physischen Gerät zu finden und kann vier primäre Partitionen enthalten.

-> 32 Bit logische Blockadresse

# GPT
**GPT** ist der neuere Ansatz für Laufwerkpartitionierung und kann mehr Partitionen verwalten und läuft insgesamt deutlich schneller.

Eigenschaften:
 - Maximal 128 Partitionen.
 - 64 Bit für logische Blockadressen.
 - Verwendet GUID.

# Paritionen verwalten
Um unter [[Linux]] Partitionen zu verwalten, kann das Programm `parted` genutzt werden.

## Auflisten aller Partitionen auf einem Laufwerk
**Direkt**
```bash
[user@host ~]$  parted /dev/vda print
```
oder **Interaktiv**
```bash
[user@host ~]$ parted /dev/vda
GNU Parted 3.2
Using /dev/vda
... omitted...
(parted) print
```

Standardmässig zeigt `parted` alle Grössen in Zehnerpotenz an (KB, MB, GB), dies kann über die Option `unit` mit den Argumenten:
- `s` -> Sektoren
- `B` -> Byte
- `MiB` 
- `GiB`
- `TiB`
```bash
[user@host ~]$  parted /dev/vda unit s print
```

## Label erstellen
Um ein neues Laufwerk zu Partitionieren muss zuerste ein Label erstellt werden:
 ```bash
 [user@host ~]$ parted /dev/vdb mklabel msdos # mbr
 [user@host ~]$ parted /dev/vdb mklabel gpt
 ``` 
## Erstellen einer Partition
```bash
[user@host ~]$ parted /dev/vda
GNU Parted 3.2
Using /dev/vda
... omitted...
(parted) mkpart
Partition name? backup   # nur bei gpt
Partition type? xfs
Start? 2048s
End? 1000MB
(parted) quit
```
## Partition löschen
```bash
[user@host ~]$ parted /dev/vda
GNU Parted 3.2
Using /dev/vda
... omitted...
(parted) pint
Disk Flags:

Number   Start     End     Size   File system   Name   Flags
2        1048kB    1049kB  512B                 backup
1        1049kB    1000MB  999MB  xfs           backup
(parted) rm 1
```
## Auf Änderungen warten
Nachdem Änderung mit `parted` vorgenommen werden, muss gewartet werden, bis diese Änderung auf die Laufwerke übernommen werden.
Dies passiert mit dem [[Prompt|Befehl]] `udevadm settle`

## Dateisystem erstellen
Nachdem das Blockgerät partitioniert ist, muss das File-System auf der Partition erstellt werden.

```bash
[user@host ~]$ mkfs.xfs -f /dev/sdb1
```
