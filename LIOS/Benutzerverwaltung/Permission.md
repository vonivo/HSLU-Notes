Datei- oder Verzeichnisberechtigungen steuern den Zugriff auf Dateien und Verzeichnisse. [[Linux]]-Dateiberechtigungen sind einfach und flexibel, leicht zu verstehen und zu implementieren, aber dennoch für viele Berechtigungsfälle ausreichend.

# Berechtigungen
In [[Linux]] existieren die Berechtigungen **read, write** und **execute** (r,w,x). Dabei haben diese Berechtigungen andere Bedeutungen wenn sie auf einem Verzeichnis oder einer Datei angewendet werden.

Die Berechtigungen werden dabei binär Kodiert:
- read -> 4
- write -> 2
- execute -> 1

**Beispiel**
Berechtigung 7 -> rwx
Berechtigung 6 -> rw-
Berechtigung 5 -> r-x


## Datei
- **read** -> Die Datei kann zum Lesen geöffnet werden. Anwender kann Inhalt lesen, aber nicht verändern.
- **write** -> Anwender kann den Inhalt einer Datei verändern. Er hat dadurch nicht das Recht, den Namen der Datei zu ändern oder zu löschen.
- **execute** -> Der Anwender kann die Datei als ein Programm ausführen. (Bei Binären-Datein und [[Scripts]] notwendig um auszuführen)

## Verzeichnis
- **read** -> Anwender kann den Inahlt eines Verzeichnisses lesen. (`ls` zeigt Inahlt an)
- **write** -> Anwender hat das Recht Dateien im Verzeichnis zu löschen, umzubenennen und zu erstellen. (In heutigen Systemen kann, muss ein Anwender `rwx` besitzen, um löschen, umbenennen oder erstellen zu können).
- **execute** -> Der Nutzer kann in das Verzeichnis wechseln, mit `cd`.

# Rechte Zuordnung
Bei [[Linux|Linuxsystemen]] können Berechtigungen auf drei Arten zugeordnet werden:
1. Besitzer/Eigentümer einer Datei ([[Nutzerverwaltung|Benutzer]]) -> user
2. Besitzende Gruppe ([[Benutzergruppe]]) -> group
3. Rest der Welt -> other

Jeder dieser Berechtigungsarten können die Berechtigen `read`, `write` und `execute` zugeordnet werden.

Ein Benutzer erhält immer nur die Rechte einer Art.
- mindestens Besitzer der Datei -> user
- Mitglied der Besitzandengruppe -> group
- übrige -> other

Die Berechtigungen einer **Datei** sieht folgendermassen aus:
```bash
[labstudent@lios-1 ~]$ ls -l
-rw-rw-r--. 1 labstudent root 0 Mar 25 08:06 test.txt
```
Der erste `-` zeigt an, dass es sich um ein File handelt.

**Verzeichnis**
```bash
[labstudent@lios-1 ~]$ ls -l
drw-rw-r--. 1 labstudent root 14 Mar 25 08:06 test
```
Der erste `d` zeigt an, dass es sich um ein Verzeichnis handelt.

Danach Folgen die Berechtigungen sowol der Eigentümer und die besitzende Gruppe:

| `-`                                                                                                                                                                    | `rw-` | `rw-` | `r--`  | `labstudent` | `root`            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----- | ----- | ------ | ------------ | ----------------- |
| - -> File<br>d -> dir<br>l -> [[UNIX-Links\|Link]]<br>b= blockorientierte Gerätedatei<br>s = Unix-Domainsocket<br>p = Named pipe<br>c = zeichenorientierte Gerätedatei | User  | Group | Others | Eigentümer   | Besitzende Gruppe |

# Änderung von Berechtigungen
Die Rechte einer Datei können immer von root-Benutzer oder vom Eigentümer geändert werden.

Ändern der Rechte:
`chmod`
- Wer -> u,g,o,a für user, group, other, all
- Wie -> +,-,= für hinzufügen, entfernen, setzen,
- Was -> r,w,x

Alterntiv kann für das sezten auch die Binäreschreibweise benutzt werden z.B  `755` -> `rwx-r-xr-x.

# Ändern der Eigentümerschaft
Die Eigentümerschaft muss in der Regel durch den root-Benutzer geändert werden.
Eine Ausnahme hierfür ist, der Benutzer kann die besitzende Gruppe ändern wenn der er Zielgruppe angehört.

`chown <user>:<group>`

Das Ändern der Eigentümerschaft bei einem [[UNIX-Links|symbolischen Link]] wird das Link-File unverändert belassen, dafür jedoch das Link-Zile ändern. (kann mit `-h` überschrieben werden.)


# Special Bits
Neben den Standardrechten exisitert pro Berechtigungsart noch ein zusätzliches Bit, das sogenannte Special-Bit.

**SID**
Das Spezialbit für die Eigentümer-Berechtigungsart legt fest (falls gesetzt), dass der Benutzer beim Ausführen der Datei die Rechte des Datei-Eigentümers erhält. (Bsp. `passwd`).

Anzeige -> `rws` falls `x`-Recht, `rwS`  falls kein `x`-Recht.

**GID**
Das Spezialbit für die besitzende Gruppe ist für Verzeichnisse und legt fest, dass die besitzende Gruppe eines Verzeichnisses vererbt wird, wenn ein neues File darin erstellt wird.

Anzeige -> `rws` falls `x`-Recht, `rwS`  falls kein `x`-Recht.

**Sticky Bit**
Das Spezialbit für die Others-Berechtigungsart ist ebenfalls für Verzeichnisse und legt fest, dass nur der Besitzer einer Datei diese auch löschen kann.