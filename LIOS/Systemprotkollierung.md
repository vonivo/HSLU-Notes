Prozesse und der [[Linux]]-Kernel zeichnen Ereignisse mittels Protokolle auf. Diese Protokolle werden für das System-Autistin und die Fehlersuche genutzt.

Der Standort dieser Logdateien ist meistens in `/var/log` und können mit normalen Textprogrammen wie `less` gelesen werden.

Generell umfasst die Protokollierungssysteme die Dienste:
- `systemd-journald`
- `rsyslog`

# `systemd-journald`
`systemd-journald` ist das zentrale Element der Ereignisprotokollierungsarchitektur. Es erfasst Meldungen von vielen Quellen, wie z.B.
- Kernel
- Ausgaben aus frühen Stadien des Bootvorgangs
- Standardausgaben und Standardfehler von Diensten bei Start und Ausführungen
- Syslog-Ereignisse.
Diese Journal wird im Dateisystem gespeichert, das nach dem Bootvorgang nicht bestehen bleibt.

# `rsyslog`
`rsyslog` liest Syslog-Meldungen, die von `systemd-journald` empfangen werden, sortiert sie und schreibt sie in Protokolldateien, welche nach Bootvorgängen in `/var/log` erhalten bleiben.


# Bekannte Protokolldateien

| Protokolldatei      | Beschreibung und Inhalt                                                                                                                                                                                                                                                 |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `/var/log/messages` | Zeit allgeimene Meldungen und Informationen zum System an. Im Grunde ein Datenprotokoll aller Aktivitäten im gesamten System, ohne Meldungen zur Authentifizierung, für die E-Mail-Verarbeitung, zur Ausführung terminierter Jobs.<br>In Debian unter `/var/log/syslog` |
| `/var/log/secure`   | Authentifizierungsprotokolle sowohl für erfolgreiche als auch für fehlgeschlagene Anmeldungen.                                                                                                                                                                          |
| `/var/log/boot.log` | Startmeldungen und Startinformationen. Konsolenmeldungen im Zusammenhang mit dem Systemsrtart nicht von Syslog                                                                                                                                                          |
| `/var/log/cron`     | Meldungen zu wiederkehrenden Aufgaben                                                                                                                                                                                                                                   |
| `/var/log/maillog`  | Für Mailserver-Protokolle                                                                                                                                                                                                                                               |

# Rsyslog
## Aufbau
Eine Syslogmeldung besteht aus drei Komponenten:
- Selektor
- log-Header
- Inhalt.

### Selektor
Ein Selektor ist eine Ganzzahl, die sich in zwei Teile zerlegen lässt:
1. Severity-Feld
2. Facility-Feld

| Severity        | Beschreibung                                                                               |
| --------------- | ------------------------------------------------------------------------------------------ |
| 0 Emergency     | Systemkritisch. Beinflusst das System, sodass das System nicht mehr verwendet werden kann. |
| 1 Alert         | Fehler, die behlben werden müssen                                                          |
| 2 Critical      | Schwerer Fehler                                                                            |
| 3 Error         | Es lag ein Fehler vor                                                                      |
| 4 Warning       | Warnung bei der Nutzung von einem Dienst                                                   |
| 5 Notice        | Auftreten eiens Ereignisses                                                                |
| 6 Informational | Information für die Nutzung                                                                |
| 7 Debug         | Debugging-Meldung über Ablauf eines Programmes oder Dienst                                 |

| Facility | Name     |
| -------- | -------- |
| 0        | Kernel   |
| 1        | User     |
| 2        | Mail     |
| 3        | Daemon   |
| 4        | Auth     |
| 5        | Syslog   |
| 6        | lpr      |
| 7        | news     |
| 8        | uucp     |
| 9        | cron     |
| 10       | authpriv |
| 11       | ftp      |

Der Selektor wird nun berechnet, indem zuerst das Facility-Feld mit 8 multipliziert und dann der numerische Wert der Schwere hinzugefügt wird.

### Logheader
Der Logheader enthält Zeitstempel sowie Name oder Hostname des Absenders
```bash
<165>1 2003-10-11T22:14:15.003Z mymachine.example.com su - ID47 [exampleSDI@234 iut="3" eventSource="" eventId="1001"] BOMAn apllication log entry
```
![[Syslog.png]]

## Konfiguration
Rsyslog gruppiert Meldungen nach dem Selektor mit Facility-Feld und Severity-Feld:
`autpriv.*    /var/log/secure`

Diese Regeln werden im File `/etc/rsyslog.conf` gespeichert.
Wenn mehrere Regeln zutreffen, erscheint die Meldung auch in mehreren Protokollen.

>[!info]
>Mit dem Programm `logrotate` können die Protokolldateien so rotiert werden, dass sie nicht zu viel Speicher benötigen. (Ab einer Grösse und Alter werden Dateien umbenannt, mit Zeitstempel versehen und später gelöscht.)


# Systemd-Journald
Systemd-journald speichert Protokolldaten in einer strukturierten, indizierten Binärdatei.
Diese Binärdatei wird unter `/run/log/journal` gespeichert -> bei Bedarf mit `rsyslog` wegsichern.

>[!info]
>In der Datei `/etc/systemd/journald.conf` kann der Parameter `Storage` gesetzt werden. Dadurch sind historische Daten auch nach dem Boot verfügbar. (Werden jedoch nach einer gewissen Zeit und ab einer bestimmten Grösse gelöscht.)




