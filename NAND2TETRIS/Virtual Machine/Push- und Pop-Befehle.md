>[!Definition]
>Die [[Stack-Machine]] kennt zwei Speicherzugriffsbefehle:
>- `push segment index`: Schreibt den Wert von `segment[index]` auf den Stack
>- `pop segment index`: Entnimmt den obersten Stackwert und speichert in in `segment[index]`

Die Segmente sind in [[Virtuelle Speichersegmente]] genauer beschrieben.
Der `index` muss dabei einer nicht-negativen ganzen Zahl entsprechen.

**Implementation**
Push Allgemein:
```
@SP
A=M
M=D

@SP
M=M+1
```

`push <segment> <index>`
```
@<index>
D=A          // setze index in D
@<segment>     // Berechnen des Offset und speicher der Adresse in D
A=M+D
D=M

@SP
A=M
M=D          // push d

@SP
M=M+1
```

Spezialfall `push constant <nunber>`
```
@<number>
D=A          // lade konstante in D

@SP
A=M
M=D          // push d

@SP
M=M+1
```