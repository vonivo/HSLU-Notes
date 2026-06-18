Damit der VM-Code einfach rechnen kann, stehen im virtuelle Speichersegmente zur Verfügung:
- `argument`: Steht für die Argument der Funktion
- `local`: Steht für die lokalen Variablen der Funktion
- `static`: steht für die Statischen Variablen, die von der Funktion gesehen werden
- `constant`: Steht für die Konstanten Werte $0,1,2,\dots,32767$
- `this`
- `that`
- `pointer`
- `temp`

Diese Symbole stehen für die Basis-Adressen innerhalb des Memories.

Beispiel:
`let x = y`
- `x` ist eine lokale Variable auf `local 1`
- `y` ist eine Feldvariable auf `this 3`
Wird zu:
```
push this 3          // Lade y in den Stack
pop local 1          // Pop aktueller Stack-Wert in x
```


