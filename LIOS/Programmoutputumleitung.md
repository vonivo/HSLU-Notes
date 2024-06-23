Jedes Programm und jeder Prozess in [[Linux]] liest Eingaben ein und gibt verarbeitete Ausgaben aus.

Linux verwendet dabei nummerierte Kanäle, sogenannte Dateideskriptoren, um Eingaben zu erhalten und Ausgaben zu senden.

Alle Prozesse beginnen mit mindestens drei Dateideskriptoren:
1. Der Standardeingabekanal (Kanal 0 stdin) liest Eingaben von der Tastatur.
2. Der Standardausgabekanal (Kanal 1 stdout) sendet eine normale Ausgabe an das [[Terminal]].
3. Der Standardfehlerkanal (Kanal 2 stderr) sendet Fehlermeldungen an das Terminal
![[LinuxProgrammKanäle.png]]

Mithilfe der Kanalnummern lassen sich nun Eingaben/Ausgaben umleiten

| Nummer   | Name        | Beschreibung                            |
| -------- | ----------- | --------------------------------------- |
| 0        | stdin       | Eingabe zum Prozesse (z.B. Tastatur)    |
| 1        | stdout      | Normale Ausgabe                         |
| 2        | stderr      | Ausgabe von Fehlern                     |
| 3,4,5... | \<filename> | Andere Dateien zum Lesen oder Schreiben |
**Anwendungsfall**
- Outputumleitung nach `/dev/null` (ignorieren)
- Outputumleitung in Datei (Speicherung)

## Beispiel
Um die Standardausgabe eines Befehls umzuleiten, verwendet man den Kanal "1" mit dem Umleitungsoperator `>`
```bash
[labstudent@lios-1 ~]$ ls 1> stdout.txt
```
Der obige Befehl schreibt den Output von `ls` nach `stdout.txt`.

Um den Standardfehler umzuleiten, wird analog der Kanal "2" verwendet.

Wenn mehrere Kanäle umgeleitet werden sollen, kann dies ganz einfach kombiniert werden:
```bash
[labstudent@lios-1 ~]$ ls 1> stdout.txt 2> stderr.txt
```



| Verwendung          | Beschreibung                                                                                   |
| ------------------- | ---------------------------------------------------------------------------------------------- |
| `> file`            | Umleitung stdout in Datei -> Datei wird überschrieben                                          |
| `1> file`           | Umleitung stdout in Datei -> Datei wird überschrieben                                          |
| `>> file`           | Umleitung stdout in Datei -> stdout wird an der Datei angehängt                                |
| `2> file`           | Umleitung stderrin Datei -> Datei wird überschrieben                                           |
| `2> /dev/null`      | Verwerfen von Fehlermeldungen durch Umleiten nach `/dev/null`                                  |
| `1> file1 2> file2` | stdout wird in file1 geschrieben, Fehler nach file2                                            |
| `> file 2>&1`       | Umleitung von stdout nach File1, Umleitung von stderr nach stdout -> Datei wird überschrieben. |
| `>> file 2>&1`      | Umleitung von stdout nach File1, Umleitung von stderr nach stdout -> Datei wird ergänzt.       |
