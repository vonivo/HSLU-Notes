Vim (Vi Improved) ist ein Editor innerhalb einer [[Terminal|Konsole]].
Vim besitzt extrem viele Tastenkombinationen und kann daher das Schreiben von Dokumenten extrem beschleunigen.

Vim ist aus sehr vielen [[Linux]]-Systemen bereits vorinstalliert und kann daher viel verwendet werden.

Vim besitzt insgeamst vier Modi:
- **Insert-Mode** -> Modus um innerhalb des Dokuments zu tippen.
- **Normal-Mode** -> Standardmodus um Dokument anzusehen.
- **Visual-Mode** -> Modus um Abschnitte zu markieren.
- **Command-Mode** -> Modus um Befehle in Vim auszuführen.

![[VimModes.png]]

# Tastenkombinationen

| Tastenkobination        | Beschreibung                                |
| ----------------------- | ------------------------------------------- |
| **Normalmode**          |                                             |
| i                       | In Insert Mode wechseln                     |
| :                       | in Command Mode wechseln                    |
| v                       | In Visual Mode wechseln                     |
| Shift + V               | in Visual Mode wechseln und Zeile markieren |
| STRG + v                | In Visual Mode wechseln und Block markieren |
| p                       | Einfügen (paste)                            |
| y                       | Kopieren (y)                                |
| d                       | Löschen                                     |
| /\<Suchbegriff>         | Suche nach \<Suchbegriff>                   |
| **CommandMode**         |                                             |
| :q                      | Beenden (quit)                              |
| :w                      | Speichern (write)                           |
| :q!                     | Beenden ohne zu speichern                   |
| :help                   | Hilfe                                       |
| :e \<filename>          | Weiteres File öffnen                        |
| **Weiteres**            |                                             |
| :colorscheme \<tab>     | Farbschema wechseln                         |
| :tabedit \<tab>         | Reiter / Tabs öffnen                        |
| STRG +n                 | Autmatische Vervollständigung               |
| :Vexplore               | Dateibaum öffnen                            |
| :set spell spelllang=en | Rechtschreibprüfung                         |
