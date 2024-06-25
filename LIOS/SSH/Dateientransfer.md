# SCP
Der **Secure Copy Befehl** `scp` ist Teil von [[OpenSSH]] und kopiert Dateien von einem Remote-System aus das lokale System oder umgekehrt.
Der Befehl verwendet den SSH-Server für die Authentifizierung und die Verschlüsselung.

Das Format des Befehls:
`[user@host ~]$ scp [user@]host:/path`

Beispiel:
``[user@host ~]$ scp labstudent@lios-server:/tmp/fileOnServer.txt /location/on/host`

# SFTP
SFTP ist ein Programm um Dateien iterativ von einem SSH-Server mit dem *Secure File Transfer Protocol* hoch- und herunterzuladen.
Auch SFTP verwendet den SSH-Server für Authentifizierung und Verschlüsselung.

**Beispiel:**
```bash
sftp> mkdri hostbackup
sftp> cd hostbackup
sftp> put /etc/hosts
Uploading /etc/hosts to /hme/remotuser/hostbackup/hosts
...omitted...
sftp> get /etc/yum.conf
Fetching /et/yum.conf to yum.conf
```

# Rsync
`rsync` ist ein Programm, um Dateien zwischen Systeme zu kopieren.
Es verwendet dabei einen [[Algorithmus]] welcher die kopierte Datenmenge minimiert, indem nur geänderte Teile übertragen werden.

## Optionen

| Option            | Beschreibung                                                 |
| ----------------- | ------------------------------------------------------------ |
| `-r, --recursive` | Rekursives Synchronisieren der gesamten Verzeichnisstruktur. |
| `-l, --links`     | Synchronisieren von [[UNIX-Links\|sybmolischen Links]]       |
| `-p, --perms`     | [[Permission\|Berechtigungen]] beibehalten                   |
| `-t, --times`     | Zeitstempel beibehalten.                                     |
| `-g, --group`     | [[Benutzergruppe\|Gruppeneigentümerschaft]] beibehalten      |
| `-o, --owner`     | [[Nutzerverwaltung\|Benutzer]] beibehalten.                  |
| `-D , --devices`  | Synchronisieren von Gerätedateien                            |

## Beispiel
`rsync -av /var/log /tmp`
