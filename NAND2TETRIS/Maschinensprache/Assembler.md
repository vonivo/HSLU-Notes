>[!Definition]
>Der Assembler ist für die Umwandlung des [[Hack Assembly|Assemlby-Codes]] in binären Code zuständig.
>Symbolverwaltung gehörht zu den wichtigsten Aufgaben des Assemblers.

![[Pasted image 20260618114549.png]]

**Handhabung von Anweisungen**
Der Assembler analysiert jeden Assembler Befehl:
- zerlegt die Anweisung in ihre zugrunde liegenden Felder;
- erzeugt für jedes Feld den entsprechenden Bit-Code;
- wenn die Anweisung eine symbolische Referenz enthält, löst er das Symbol in seinen numerischen Wert auf;
- setzt die sich ergebenden Binärcodes zu einer Zeichenkette aus sechzehn 0 und 1 zusammen und
- schreibt die zusammengesetzte Zeichenfolge in die Ausgabedatei.

## Symboltabelle
Damit der Assembler weiss, welcher numerische Wert sich hinter jedem Symbol versteckt, benötigt er eine Symboltabelle. Diese Symboltabelle wird zu Beginn mit den vordefinierten Symbolen initialisiert:

| Symbol   | Adresse |
| -------- | ------- |
| `R0`     | 0       |
| `R1`     | 1       |
| `R2`     | 2       |
| ..       | ...     |
| `R15`    | 15      |
| `SP`     | 0       |
| `LCL`    | 1       |
| `ARG`    | 2       |
| `THIS`   | 3       |
| `THAT`   | 4       |
| `SCREEN` | 16384   |
| `KDB`    | 24576   |
Diese Tablle wird dann mit zwei weiteren Durchgängen vervollständigt.
1. Im ersten Durchgang geht der Assembler den Code Zeile für Zeile durch und merkt sich die Zeilennummer (Startet bei 0 und wird nur bei jedem [[A-Befehl]] oder [[C-Befehl]] erhöht). Jedes Mal, wenn der Assembler auf eine Label-Deklaration `(myLabel)` stösst, fügt er dieses Label der Symboltabelle mit der aktuellen Zeilennummer + 1 hinzu. (ROM-Adresse des nächsten Befehls)
2. Im zweiten Durchlauf geht der Assembler erneut Zeile für Zeile durch den Code. Jedes Mal, wenn er einen [[A-Befehl]] mit einem symbolischen Verweis sieht, ersetzt er dieses Symbol mit der entsprechende Adresse. Ist das Symbol noch in der Symbol-Tabelle enthalten, fügt er es hinzu mit der nächst freien ROM-Adresse.



## Implementation
- Der Assembler akzeptiert ein einziges Kommandozeilenargument, wie folgt: `prompt> HackAssembler Prog.asm` (`.asm` obligatorisch, bei keinem Pfad wird mit dem Ordner gearbeitet.)
- Es wird eine neue Datei erstellt welche `Prog.hack` heisst und allenfalls bestehende Dateien überschreibt.

### Parser-Modul
- Das Paser-Modul parst die Eingabe in Anweisungen und wiederum in Felder.
- Ignoriert Kommentare und Leerzeichen in Eingabestrom.
- Ermöglicht zeilenweiser Zugriff auf die Eingabe und zerlegt symbolische Anweisungen in zugrunde liegende Komponenten.

| Routine         | Argumente  | Ruckgabe                                        | Funktion                                                                                                                                                                                                                      |
| --------------- | ---------- | ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Konstruktor     | Input Date |                                                 | Öffnet die Eingabedatei und bereitet sie zum Parsen vor.                                                                                                                                                                      |
| hasMoreLines    |            | boolean                                         | Gibt es weitere Zeilen in der Eingabe?                                                                                                                                                                                        |
| advance         |            |                                                 | Überspringt Leerraum und Kommentare, falls erforderlich. Liest die nächste Anweisung aus der Eingabe und macht sie zur aktuellen Anweisung. Diese Routine sollte nur aufgerufen werden, wenn hasMoreLines wahr ist.           |
| instructionType |            | A_INSTRUCTION<br>C_INSTRUCTION<br>L_INSTRUCTION | Gibt den Typ der aktuellen Anweisung zuruck:<br>- A_INSTRUCTION für @xxx, wobei xxx eine Dezimalzahl oder ein Symbol ist<br><br>- C_INSTRUCTION für dest=comp;jump<br><br>- L_INSTRUCTION für (xxx), wobei xxx ein Symbol ist |
| symbol          |            | string                                          | Für die aktuelle Anweisung (xxx) wird das Symbol xxx und fü @xxx wird das Symbol oder die Dezimalzahl xxx als Zeichenkette zurückgegeben.                                                                                     |
| dest            |            | string                                          | Gibt den symbolischen dest Teil der aktuellen C-Anweisung zurück (8 Symbole).                                                                                                                                                 |
| comp            |            | string                                          | Gibt den symbolischen comp Teil der aktuellen C-Anweisung zuruck (28 Symbole).                                                                                                                                                |
| jump            |            | string                                          | Gibt den symbolischen jump Teil der aktuellen C-Anweisung zuruck (8 Symbole)                                                                                                                                                  |


### Code-Modul
Das Code-Modul bietet Dienste für die Übersetzung symbolischer Hack Mnemonics in ihre Binärcodes.

Alle $n$-Bit-Codes werden als Zeichenkette mit 0 und 1 zurückgegeben.
- Ein Aufruf von `dest("DM")` ergibt `011`
- Ein Aufruf von `comp("A+1")` ergibt `110111`
- etc.

| Routine         | Argumente | Ruckgabe                                        | Funktion                                                                                                                                                                                                                      |
| --------------- | --------- | ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dest            | string    | 3-bit als string                                | Gibt den Binärcode des dest Mnemonics zuruck.                                                                                                                                                                                 |
| comp            | string    | 7-bit als string                                | Gibt den Binärcode des comp Mnemonics zuruck                                                                                                                                                                                  |
| jump            | string    | 3-bit als string                                | Gibt den Binärcode des jump Mnemonics zuruck.                                                                                                                                                                                 |

