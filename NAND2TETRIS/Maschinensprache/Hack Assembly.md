Die Maschinensprache der [[Hack Maschine]] heisst Hack-Assembly.

**Adressräume**
Hack kennt zwei Adressräume:
- Befehlsspeicher
- Datenspeicher
Beide Speicher sind **16 Bit breit** und haben einen **15-Bit Adressraum** ($2^{15}$ adressierbare Wörter).

**Register**
Hack kennt die beiden Register **A** und **D**, welche explizit durch arithmetische und logische3 Anweisungen manipuliert werden können.

### Konzeptionelles Modell
Das konzeptionelle Modell der Hackplattform sieht wie folgt aus:
![[Pasted image 20260616192754.png]]

### Befehle
Hack kennt zwei Arten von Befehlen:
- [[A-Befehl]]
- [[C-Befehl]]


## Vordefinierte Symbole

#### Virtuelle Register
Um die Assemblerprogrammierung zu vereinfachen werden die virtuellen Register `R0` bis `R15` vordefiniert, welche den RAM-Adressen $0$ - $15$ zugewiesen werden.

#### Vordefinierte Zeiger
Die Symbole `SP`, `LCL`, `ARG`, `THIS`, `THAT` sind ebenfalls vordefiniert und beziehen sich auf die RAM-Adressen $0$ - $4$.
#### I/O-Zeiger
Die Symbole `SCREEN` und `KDB` sind vordefiniert und zeigen auf die RAM-Adressen $16384=(4000)_{h}$ bzw. $24576=(6000)_{h}$.

## Bezeichnungssymbole
Bezeichnungssymbole sind benutzerdefiniert und dienen dazu, Ziele von goto-Befehlen zu kennzeichnen.
Bezeichnungssymbole werden durch `(Xxxx)` definiert und druch `Xxxx` wiederverwendet.

**Variablen**
Jedes benutzerdefinierte Symbol `Yyyy` welches nicht vordefiniert ist und nicht an anderer Stelle mit `(Yyyy)` definiert ist, wird als Variable behandelt und erhält vom Assembler eine eindeutige Speicheradresse, beginnend bei RAM-Adresse $16$


## Pheripherie
### Bildschirm
Der Bildschirm des Hack-Computers besteht aus $256$-Zeilen mit $512$ Pixeln pro Zeile. Der Inhalt des Bildschirms wird durch einen 8K-Speicherabbildung dargestellt, die bei der RAM-Adresse $16384$ beginnt.
Jede Zeile des Bildschirms, beginnen mit der oberen linken Ecke, wird im RAM durch $32$ aufeinanderfolgende 16-Bit-Wörter dargestellt.

Das Pixel in der Zeile $r$ von oben und der Spalte $c$ von links wird auf das $c\%16$-Bit des Wortes unter $RAM\left[ 16384+r*32+\frac{c}{16} \right]$ abgebildet.
![[Pasted image 20260616203440.png]]

### Tastatur
Der Hack-Computer benutzt eine ASCII-Tastatur. Jedes Mal, wenn eine Taste gedrückt wird, wird der entsprechende ASCII-Wert in $RAM[24576]$ geschrieben. Zusätzlich zu den ASCII-Codes werden folgende Tasten erkannt:
![[Pasted image 20260616203643.png]]


## Dateiformat
Binärcodedateien bestehen aus Textzeilen. Jede Zeile ist eine Folge von sechzehn 0 und 1 ASCII-Zeichen.

Die Dateiendung lautet `.hack`.

Das Assemblerprogramm ist eine Textdatei mit der Erweiterung `.asm`. Die Datei besteht aus Textzeilen, von denen jede entweder ein Befehl, Kommentar oder eine Symboldeklaration darstellt.

- Alle MNemoics müssen in Grossbuchstaben geschrieben sein.
- Symbole sind Case-sensitive
- Konstanten müssen nicht-negativ sein und werden in dezimaler Notation geschrieben.
- Symbole kann eine beliebige Folge von Buchstaben, Ziffern, Unterstich, Punkt, Dollarzeichen und Doppelpunkt sein die nicht mit einer Ziffer beginnt.
- Kommentare werden mit `//` gekennzeichnet und verhalten sich wie in Java.
- Leerzeichen und leere Zeilen werden ignoriert.
