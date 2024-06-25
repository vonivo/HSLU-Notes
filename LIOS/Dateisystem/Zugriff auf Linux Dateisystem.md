Der Zugriff auf ein [[Linux]] [[Dateisystem]] erfolgt über den Dateibaum.
Externe Festplatten oder andere Dateisysteme werden in diesem Baum eingefügt.

Bei weiteren Dateisystemen wird ein Verzeichnis eingefügt, anstelle des Blockgeräts. (Meist unter `/mnt`)

=> Vorteil: Blockgeräte lassen sich mit standard Bordmitteln verwalten (z.B. `ls` oder `cp`)

## Benennung

| Typ                                    | Gerätebenennungsmuster         |
| -------------------------------------- | ------------------------------ |
| SATA/SAS/USB                           | `/dev/sda`, `/dev/sdb`,...     |
| virio-blk paravirtualisierter Speicher | `/dev/vda`, `/dev/vdb`,...     |
| NVMe                                   | `/dev/nvme0`, `/dev/nmve1`,... |
| SD/MMC/eMMC                            | `/dev/mmcblk0`, `/dev/mmcblk1` |
**Gerät** -> `/dev/XY`
**Mountpoint** -> Verzeichnis, z.B. `/mnt`

# Partition
Eine Partition ist ein eigenständiges *logisches* Blockgerät.
Bei Laufwerken, welche über SATA angeschlossen sind, erfolgt die Benennung so:
- Erste Partition auf Gerät `/dev/sda` -> `/dev/sda1`
- Zweite Partition auf Gerät `/dev/sdb` -> `/dev/sdb2`

Dateisysteme aufzeigen:
`[user@host ~]$ df -h`

# Files suchen
## `locate`
Das Programm `locate` sucht ein File bei seinem Namen und benutzt dazu eine Datenbank. Diese Datenbank muss jedoch zuerst erstellt werden.

`[user@host ~]$ updatedb`
`[user@host ~]$ locate test.txt`

## `find`
`find` Durchsucht den gesamten Dateibaum, was etwas länger dauert. Dafür muss keine DB erstellt werden.

>[!error] Achtung
>Wer in `find` Wildcards verwendet, muss den Namen in `''` setzen, da ansonsten die [[Bash Shellextension]] benutzt wird.



