# `at`
Mit dem [[Prompt|Befehl]] `at`kann ein Job geplant werden:
`at <Zeitangabe>`. Danach wird der Benutzer aufgefordert die Befehle manuell einzutippen.
Wenn er fertig ist muss **STRG+D** gedrückt werden.

Damit die Befehle nicht manuell eingegeben werden, lohnt es sich, die Befehle via [[Programmoutputumleitung|Inputumleitung]] einzuspeisen.

**Beispiel**
```bash
[user@host ~]$ at now +10min
warning command will be executed usin /bin/sh
at> echo "date: $(date)"
at> <EOT>
Job 7 at Fir May 20 00:23:00 2024
[user@host ~]$ atq
7           Fir May 20 00:23:00 2024 a root
```
![[ZeitangabenAt.png]]

# `crontab`
Der Cron-[[Daemon]] ist ein Dienst, der automatisch und periodisch Skripte und Programm zur vorgegebenen Zeit starten kann.

Die auszuführenden Aufgaben werden in einer Datei festgehalten.
- `/etc/crontab` -> Systemweit, nur mit root-Rechten bearbeitbar
- `/var/spool/crontabs/` -> Verzeichnis für Benutzerspezifische `crontab`-Dateien

```bash
#M   S     T M W    Befehl
#-------------------------------------------------------------
5    9-20  * * *    /home/voiv/scripts/script1.sh > /dev/null
*/10 *     * * *
59   23    * * 0,4

```

Der Crontab besteht aus sechs Spalten. Die ersten fünf ist eine Cron-Expression und die Lezte den auszuführenden Befehl.

CronExpression:
1. Minute
2. Stunde
3. Tag
4. Monat
5. Wochentag

Im Obigen Beispiel:
1. Fünf Minuten nach jeder vollen Studen zwischen 9 und 20 Uhr.
2. Alle 10 min
3. Jeden Sonntag und Donnerstag um 23:59

## Crontabs für Root
Global wiederkehrende Jobs sollten nicht in `/ect/crontab` definiert werden, sondern im Verzeichnis `/etc/corn.d/`, da so sichergestellt wird, dass die Jobs nacheinem Pakett update nicht überschrieben werden.

Zusätzlich zu der normalen Crontab-Datei besitzt die Root-Corntab-Datei noch eine Spalte für den Benutzer mehr:
```bash
#M   S     T M W    Benutzer  Befehl
#-------------------------------------------------------------
5    9-20  * * *    root      /home/voiv/scripts/script1.sh > /dev/null

```

## [[Systemd]]
Auch mit Systemd können wiederkehrende Jobs erstellt werden.

Timer sind systemd-Units, die auf `.timer` enden und die `.service`-Dateien oder Ereignisse steuern.

Damit die Timer-Unit eine andere Unit aktiviert, muss der Name der Unit gleich sein.
Die Ereignisse werden im [[Logging|Systemjournal]] gespeichert.
