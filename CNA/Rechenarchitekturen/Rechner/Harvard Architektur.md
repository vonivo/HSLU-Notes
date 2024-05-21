Die Harvard Architektur bietet im Vergleich zu der [[Von-Neuman-Architektur]] einen separaten Speicher für Befehle und Daten, welche auch über separate Busse angesprochen werden.
![[Harvard-Architektur.png]]
## Vorteile
- Gleichzeitige Zugriffe auf beide Speicher
- Im Idealfall kann **in einem Taktzyklus Befehle und Daten laden**
- Synchrones Laden mit mehreren Rechenwerken
- Strikte **Trennung** von Daten und Programm -> Speicherschutz und einfache Trennung der Zugriffsrechte
- Datenwort- und Speicherwortgrösse unabhängig voneinander


Benutzt wird die Harvard-Architektur von Mikrocontroller ([[8051]], PIC, AVR) und von vielen [[Spezialprozessoren#DSP Digitaler Signalprozessor|Digitalen Signalprozessoren]].
Heutige Prozessoren verwenden meistens eine Mischform von Harvard und [[Von-Neuman-Architektur|von Neuman]].