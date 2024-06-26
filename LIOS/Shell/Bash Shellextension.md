Die Bash Shellextension ist ein Mechanismus der [[Bash]] um einen [[Prompt|Befehl]] zu erweitern.


Das bedeutet, dass z.B. ein Dateiname ergänzt oder vervollständigt werden kann, oder man einen Platzhalter eingibt, welcher dann ersetzt wird.

In UNIX-Zeiten wurde das Ersetzen von Platzhaltern über das separate Programm "Glob" realisiert, heute wird dafür die Bibliothek `glob()` zur Verfügung gestellt.

Beispiel:
```bash
[labstudent@lios-01 ~]$ mv *.txt textfiles/
```


| Muster        | Wirkung                                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------- |
| `*`           | Eine Zeichenfolge mit null oder mehreren Zeichen                                                                      |
| `?`           | Jedes einzelne Zeichen                                                                                                |
| `[abc]`       | Jedes Zeichen in der eingeschlossenen Klasse (eckige Klammern)<br>Beispiel: `[ab]test.txt]` -> `atest.txt, btest.txt` |
| `[^abc]`      | Alle nicht eingeschlossenen Klassen (Negation)                                                                        |
| `[[:alpha:]]` | Alle Zeichen des Alphabets                                                                                            |
| `[[:lower:]]` | Alle Zeichen in Kleinbuchstaben                                                                                       |
| `[[:upper:]]` | Alle Zeichen in Grossbuchstaben                                                                                       |
| `[[:alnum:]]` | Alle Zeichen des Alphabets oder Ziffern                                                                               |
| `[[:punct:]]` | Alle druckfähigen Zeichen, keine Leerzeichen oder alphanumerische Zeichen                                             |
| `[[:digit:]]` | Ziffer von 0 bis 9                                                                                                    |
| `[[:space:]]` | Jeder einzelne Leerraum. Dazu zählen Tabulatoren, Zeilenumbrüche, Absatzwechsel, Setienvorschub oder Leerzeichen.     |
