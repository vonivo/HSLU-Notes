- Das eingabe Dateiformat ist ein Text-Dokument welches mit `.vm` endet.
- Erzeugt wird ein Text-Dokument welches auf `.asm` ([[Hack Assembly]]) endet.

>[!Info]
>Nachfolgend wird der VM-Translator zum spezifischen Hack-Assembly beschrieben.

## Datentypen
Die VM Abstraktion hat nur einen Datentyp: **vorzeichenbehaftete Ganzzahlen**.
Auf der [[[Hack Maschine|Hack Plattform]] als 16-Bit-Wert im [[Binäre Addition|Zweier-komplement]] gespeichert.
Boolesche Werte `true` und `false` werden als `-1` bzw. `0` dargestellt.


## RAM Nutzung
Die Implementation der VM nutzt den oberen Teil des RAM wie folgt:

| RAM Adresse | Verwendung            |
| ----------- | --------------------- |
| $0 - 15$    | 16 virtuelle Register |
| $16-255$    | statische Variablen   |
| $256-2047$  | Stack                 |

### Virtuelle Register

| Name     | Speicherort  | Verwendung                                                                                 |
| -------- | ------------ | ------------------------------------------------------------------------------------------ |
| `SP`     | `RAM[0]`     | Speicheradresse unmittelbar nach der Speicheradresse, die den obersten Stack-Wert enthält. |
| `LCL`    | `RAM[1]`     | Basisadresse für `local`-Segment (siehe [[Virtuelle Speichersegmente]])                    |
| `ARG`    | `RAM[2]`     | Basisadresse für `argument`-Segment                                                        |
| `THIS`   | `RAM[3]`     | Basisadresse für `this`-Segment                                                            |
| `THAT`   | `RAM[4]`     | Basisadresse für `that`-Segment                                                            |
| `TEMP`   | `RAM[5-12]`  | Basisadresse für `temp`-Segment                                                            |
| `R13-15` | `RAM[13-15]` | Freie Register für die Assembler Code Erzeugung                                            |
>[!Info]
>Basisadresse eines Segments beschreibt die physische Adresse im Host-RAM.

Der VM-Code nutzt nie physische Adressen, stattdessen werden nur symbole Verwenden.
z.B. um den Inhalt von dem Register `D` auf den Stack zu schieben: `RAM[SP++]=D`. wird dann zu:
```
@SP
A=M          // lade sie Stackaddresse in `A`
M=D          // Schreibe in M (RAM[A]) den Inhalt von D
@SP
M=M+1        // erhöhe den SP
```

### Pointer / THIS & THAT
Das `pointer`-Segment enthält genau zwei Werte und wird direkt auf die RAM Speicherplätze $3$ und $4$ abgebildet. Ebenfalls werden `THIS` und `THAT` auch auf $3$ bzw. $4$ abgebildet.

Somit ist jeder Zugriff azuf `pointer 0` ein Zugriff auf `THIS` und `pointer 1` auf `THAT`.

Die Basisadresse von `POINTER` ist immer 3, wohingegen die Basisadresse von `THIS` in `RAM[3]` gespeichert ist.

### TEMP
Diese 8-Wort-Segment ist ebenfalls fest und wird direkt auf RAM $5-12$ abgebildet.
Sprich die Basisadresse von `TEMP` ist `5` und `i` liegt zwischen $0-7$.

### CONSTANT
Diese Speichersegment ist wirklich virtuell, da es keinen physischen RAM Speicher belegt. Stattdessen behandelt die VM Implementierung jeden Zugriff auf `constant i` indem sie einfach die Konstante `i` bereitstellt.

Der Befehl `push constant 17` soll in Assemblercode übersetzt werden, indem der Wert `17` auf den Stack geschoben wird.

### STATIC
Statische Variablen werden auf der RAM Adressen $16-256$ abgebildet.

Jeder Verweis auf `static i` in einem VM-Programm das in `Foo.vm` gespeichert ist, kann in das Assemblersymbol `Foo.i` übersetzt werden.
Gemäss der Spezifikation von [[Hack Assembly]] ordnet der Hackassembler diese symbolischen Variablen dem Host RAM ab der Adresse 16 zu.



## Implementation
Die Implementation wird in 3 Module aufgeteilt:
- VMTranslator
- Parser
- CodeWriter

### Parser
Der Parser behandelt die Analyse einzelner `.vm`-Dateien und bietet Dienst zum Lesen, Entpacken von VM-Befehle in verschiedene Komponenten und zum Bereitstellen des Zugriffs auf diese Komponenten.


| Routine      | Argumente   | Rückgabe                                                                                         | Funktion                                                                                                                                                                                                       |
| ------------ | ----------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Konstruktor  | Input Datei |                                                                                                  | Öffnet die Eingabedatei und bereitet sie zum  Parsen vor                                                                                                                                                       |
| hasMoreLines |             | boolean                                                                                          | Gibt es weitere Zeilen in der Eingabe?                                                                                                                                                                         |
| advance      |             |                                                                                                  | Überspringt Leerraum und Kommentare, falls erforderlich. Liest die nächste Anweisung aus der Eingabe und macht sie zur aktuellen Anweisung                                                                     |
| commandType  |             | C_ARITHMETIC, C_PUSH, <br>C_POP, <br>C_LABEL, <br>C_GOTO, <br>C_IF, C_FUNCTION, C_RETURN, C_CALL | Gibt den Typ der aktuellen Anweisung zurück. Fur arithmetische oder logische Befehle wird C_ARITHMETIC zurückgegeben.                                                                                          |
| arg1         |             | string                                                                                           | Gibt das erste Argument der aktuellen Anweisung zurück. Fur C_ARITHMETIC Anweisungen wird der Befehl (add, sub, etc.) zurückgegeben. Sollte nicht aufgerufen werden, wenn die aktuelle Anweisung C_RETURN ist. |
| arg2         |             | int                                                                                              | Gibt das zweite Argument der aktuellen Anweisung zurück. Sollte nur aufgerufen werden, wenn die aktuelle Anweisung C_PUSH, C_POP, C_FUNCTION oder C_CALL ist.                                                  |
### Code Writer
Dieses Modul übersetzt einen geparsten VM Befehl in Hackassemblercode.

| Routine         | Argumente                                           | Rückgabe | Funktion                                                                                                    |
| --------------- | --------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------- |
| Konstruktor     | Input Datei                                         |          | Öffnet die Ausgabedatei und bereitet sie zum Schreiben vo                                                   |
| writeArithmetic | command (string)                                    |          | Schreibt in die Ausgabedatei den Assembler Code, der den arithmetischen oder logischen Befehl implementiert |
| writePushPop    | command (string)<br>segment (string)<br>index (int) |          | Schreibt in die Ausgabedatei den Assembler Code, der den push oder pop Befehl implementiert.                |

### VMTranslator
Dies ist das Hauptprogramm, welches die Übersetzung mithilfe der anderen zwei Module steuert.


Der VM-Translator erstellt aus allen `.vm` Files in einem Ordener ein `.asm` File