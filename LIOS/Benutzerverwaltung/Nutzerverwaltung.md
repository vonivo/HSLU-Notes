[[Linux]] ist ein Mehrbenutzersystem.
Benutzer haben:
- einen Benutzernamen
- eine interne ID (genannt User-ID /UID)
- meistens ein Passwort
Benutzer dienen dabei:
- dem Festlegen von Dateieigentümern
- zum Ausführen von Programmen mit bestimmten Rechten.

# Benutzertypen
In Linux wird zwischen drei Benutzertypen unterschieden:
- Root -> Administrator/Superuser
- Systembenutzer
- reguläre Nutzern

### Root-User
Ein root-User verwaltet das System und besitzt immer dei UID 0. Er Bestitz vollständigen Zugriff auf das komplette System.

## Systembenutzer
Systembenutzer führen unterstützende Systemprozesse aus; kein Root sondern eingeschränkter Zugriff. Die Rechte dieser Systembenutzer sind dabei spezifisch und gezielt angesetzt, sodass nur die nötigen Ressourcen benutzt werden können. (z.B. [[OpenSSH]]-User).

Systembenutzer zeichnen sich durch eine UID von 1 bis 999 aus, wobei die UID 1-200 statisch vergeben werden und 201-999 dynamisch.

## Regulärer Benutzer
Reguläre Benutzer sind für die alltägliche Arbeit gedacht und besitzen eingeschränkten Zugriff.
Reguläre Benutzer erhalten UIDs ab 1000.


# `/etc/passwd`
Alle Benutzer eines [[Linux]] systems sind in dem File `/etc/passwd` abgelegt.
Dabei repräsentiert eine Zeile einen Benutzer.

**Beispiel:**
```bash
vonivo:x:1000:1000:Ivo von Rickenbach:/home/vonivo:/usr/bin/zsh
cups:x:209:209:cups helper user:/:/usr/bin/nologin
```
Die einzelnen Spalten sind mit einem `:` getrennt und sind folgende von links nach rechts:
- Benutzername
- Passwort -> Wird immer als 'x' dargestellt -> `/etc/shadwo`
- UID
- GID -> ID der [[Benutzergruppe|Primärgruppe]]
- realer Name
- Homeverzeichis
- Standard [[Terminal|Shell]]

# Benutzer wechseln
Um zu einem anderen Benutzer zu wechseln existieren verschieden Möglichkeiten:
 - `su` -> veraltet
 - `sudo` -> neu

**SU**
Der [[Prompt|Befehl]] `su` für switch User startet eine andere Shell Instanz mit den Rechten des Zielbenutzers (ohne Angabe -> root). Um sicherzustellen, dass der Benutzer dazu berechtigt ist, wird das Passwort des Zielbenutzers verlangt.

**SUDO**
Der [[Prompt|Befehl]] `sudo` für substitue User do verhält sich dabei völlig anders.
- Für `sudo` extistiert die Konfigurationsdatei `/etc/sudoers` welche auflistet, welche Benutzer Rechte für bestimmte Aktionen haben. (z.B. Befhel als Root ausführen)
- `sudo` fragt nach dem Passwort des Benutzers, der es startet, um sicherzustellen, dass die Person am Terminal wirklich der Benutzer ist welcher in `/etc/sudoers` aufgeführt ist.
- Die Adminrechte werden über `/etc/sudoers` oder über eine Gruppenzugehörigkeit vergeben.

### Beispiel

| Befehl                | Wirkung                                                                                                                                   |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `su`                  | Startet eine [[Terminal\|Shell]] als root im Kontext des aktuellen Nutzers (gleiche Umgebunsvariablen und gleiches aktuelles Verzeichnis) |
| `su -` `su -l`        | Startet eine neue [[Terminal\|Shell]] als root (**neues Login**). Arbeitsverzeichnis und Umgebunsvariablen werden angepasst.              |
| `su -l labadmin`      | Startet neue [[Terminal\|Shell]] als `labadmin`. Arbeitsverzeichnis und Umgebunsvariablen werden angepasst.                               |
| `sudo -i`             | Startet **neue [[Terminal\|Shell]]** wie `su -`                                                                                           |
| `sudo -s`             | Startet [[Terminal\|Shell]] als root im Kontext vom aktuellen Benutzer. (Eselbrücke s -> preserve)                                        |
| `sudo -u labadmin -i` | Siehe `su -l labadmin`                                                                                                                    |


# Benutzer verwalten
**Benutzer erstellen**
```bash
[labstudent@lios-1 ~]$ useradd <username>
```

Optionen:
- `-m, --create-home` -> Erstellt Homeverzeichnis.
- `-g, --gid` -> Legt primäre Gruppe fest.
- `-s, --shell` -> Legt Standardshell fest. 
- `-c, --comment` -> Notziz

**Benutzer ändern**
```bash
[labstudent@lios-1 ~]$ usermod <username>
```

Optionen:
- `-d, --home` -> Ändert Homeverzeichnis.
- `-g, --gid` -> Legt primäre Gruppe fest.
- `-G <liste>` -> Legt Zusatzgruppen fest. 
- `-a, --append` In Verbindung mit `-G` fügt Gruppe hinzu statt zu ersetzen.
- `-c, --comment` -> Notziz

**Benutzer löschen**
```bash
[labstudent@lios-1 ~]$ userdel -r <username>
```
-r -> Löscht Nutzerverzeichnisse.

