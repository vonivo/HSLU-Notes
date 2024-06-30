Nach eine [[Partition]] fertig erstellt wurde, muss sie noch in [[Dateisystem]] eingehängt werden. Dies geschieht über das Mounting mit dem [[Prompt|Befehl]] `mount`

**Temporäres Mounting**
```bash
[user@host ~]$ mount /dev/sdb1 /mnt/backup
```

**Permanentes Mounting**
Das permanente Mounting passiert über den File-System-Tabel in der Konfigurationsdatei `/etc/fstab`.
Jede Zeile zeigt einen Mount eintrag:
```bash
UUID=3b51d985-8211-7eb9270e873d /backup xfs  default 0 0
```
Die Optionen sind:
- `UUID` -> Id der Partition
- `/backup` -> Mount-Point
- `xfs` -> File-System
- `defaults` -> Durch Komma getrennte Liste für weitere Optionen
- `0` -> Wird vom Dump-Befehl genutzt
- `0` -> fsck-Reihenfolge-Feld (Bei xfs-Dateisystemen immer auf `0`, ext4 = 1 und root-Dateisystem=2)
