Systemd ist ein Programm zu Verwaltung von Diensten unter [[Linux]]. Der Systemd-[[Daemon]] ist der erste Prozess, der gestartet wird, mit der PID=1.

Systemd ist das Standard-Initialisierungssystem unter vielen Linux-Distros.

Wichtige Funktionen:
- paralleler Start beim Boot.
- On-Demand-Aktivierung von [[Daemon|Daemons]]
- Verwaltung von Abhängigkeiten
- Mount-Points können als systemd-Ziele konfiguriert werden.

# Units
Systemd ist in Units gegliedert, die alle einen eigenen Zweck haben:

| Typ          | Dateierweiterung | Beschreibung                                                                                                                                                             |
| ------------ | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Systemd unit | -                | Oberbegriff für alle Units                                                                                                                                               |
| Service unit | .service         | Systemdienst (z.B. openssh)                                                                                                                                              |
| Target unit  | .target          | Gruppe von Systemd-Units. Wird genutzt um Synchronisationspunkte zu erstellen (bsp Netowrk.target)                                                                       |
| Mount unit   | .automount       | Automatischer Einhängepunkt im Dateisystem                                                                                                                               |
| Socket unit  | .socket          | Kommunikation zwischen Prozessen: Wenn ein Client eine Verbindung zum Socket herstellt, startet `systemd` den entsprechenden [[Daemon]] und leitet die Verbindung weiter |

# Systemctl
Der [[Prompt|Befehl]] `systemctl` wird verwendet, um `systemd`Dienstee zu verwalten.

## Auflisten von Units
`list-unit` -> Auflisten von allen In-Memory-Units

```bash
[labstudent@lios-1 ~]$ systemctl list-units --type=service
UNIT                    LOAD   ACTIVE SUB     DESCRIPTION
accounts-daemon.service loaded active running Accounts Service
atd.service             loaded active running Job spooling tools
cloud-final.service     loaded active exited  Execute cloud user
```
- `UNIT`-> Name der Service-Unit
- `LOAD` -> Geladene Konfiguration i.O.
- `ACTIVE` -> genereller Aktivierungsstand
- `SUB` -> Weitere Informationen über Zustand.

`--all` -> Liste alle Dienste auf (nicht nur aktive).
`--type`-> Einschränkung auf Unit-Typ


`list-unit-files` -> Auflisten von allen installierte Units auf zusätzlich mit dem Enabled-Status (Autostart).

## Status
Der Status eines Dienstes abfragen:
```bash
● cups.service - CUPS Scheduler
     Loaded: loaded (/usr/lib/systemd/system/cups.service; enabled; preset: disabled)
     Active: active (running) since Tue 2024-06-25 08:48:25 CEST; 3h 4min ago
 Invocation: 6dfcb45ae27947009440300c9c6eb7c4
TriggeredBy: ● cups.path
             ● cups.socket
       Docs: man:cupsd(8)
   Main PID: 730 (cupsd)
     Status: "Scheduler is running..."
      Tasks: 1 (limit: 18854)
     Memory: 6.3M (peak: 6.8M)
        CPU: 42ms
     CGroup: /system.slice/cups.service
             └─730 /usr/bin/cupsd -l

Jun 25 08:48:25 lt-vonivo systemd[1]: Starting CUPS Scheduler...
Jun 25 08:48:25 lt-vonivo systemd[1]: Started CUPS Scheduler.
```
 => Wenn Konfigurationsdatei nicht in `/etc/systemd` ist, ist der Dienst durch eine Programminstallation hinzugekommen.

Weitere Abfragen:
- `systemctl is-active sshd.service`
- `systemctl is-enabled sshd.service`
- `systemctl is-faild sshd.service`
- `systemctl --failed --type=service` 

## Befehle

| Beschreibung                                                                                                 | Befehl                             |
| ------------------------------------------------------------------------------------------------------------ | ---------------------------------- |
| Detaillierte Informationen zu Unit azeigen                                                                   | `systemctl status UNIT`            |
| Einen Service beenden                                                                                        | `systemctl stop UNIT`              |
| Einen Service starten                                                                                        | `systemctl start UNIT`             |
| Einen Service neu starten                                                                                    | `systemctl restart UNIT`           |
| Neu laden der Konfigurationsdatei                                                                            | `systemctl reload UNIT`            |
| Das Ausführen eines Service vollständig unterbinden, sowohl durch manuelle Eingaben als auch beim Systemboot | `systemctl mask UNIT`              |
| Einen maskierten Service verfügbar machen                                                                    | `systemctl unmask UNIT`            |
| Einen Service zum Autostart hinzufügen                                                                       | `systemctl enable UNIT`            |
| Eine Service vom Autostart entfernen                                                                         | `systemctl disable UNIT`           |
| Einheiten auflisten, die zum Starten der Unit benötigt werden.                                               | `systemctl list-dependencies UNIT` |
