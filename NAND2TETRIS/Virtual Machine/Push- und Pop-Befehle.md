>[!Definition]
>Die [[Stack-Machine]] kennt zwei Speicherzugriffsbefehle:
>- `push segment index`: Schreibt den Wert von `segment[index]` auf den Stack
>- `pop segment index`: Entnimmt den obersten Stackwert und speichert in in `segment[index]`

Die Segmente sind in [[Virtuelle Speichersegmente]] genauer beschrieben.
Der `index` muss dabei einer nicht-negativen ganzen Zahl entsprechen.

