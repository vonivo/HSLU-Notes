Unterstützt die Textausgabe auf dem Bildschirm.
**API**
```java
function void moveCursor(int i, int j)
function void printChar(char c)
function void printString(String s)
function void printInt(int i)
function void println()
function void backSpace()
```

Für die Textuelle Ausgabe wird der Bildschirm in 23 Zeilen mit 64 Zeichen unterteilt.
**Zeichensatz**
![[Pasted image 20260620143906.png]]

## Schriftart
- Jedes Zeichen nimmt einen festen Rahmen von 11 Pixel Höhe und 8 Pixel Breite ein.
- Der Rahme enthält 2 leere recht Spalten und 1 leere untere Zeile für den Abstand zwischen den Zeichen
- Alle Zeichen werden als Bitmap in einem Array gespeichert
![[Pasted image 20260620144150.png|639]]
![[Pasted image 20260620144207.png]]

## Cursor
Der Cursor zeigt an, wo das nächste Zeichen geschrieben werden soll.
- newLine -> bewegt den Cursor an den Anfang der neuen Zeile.
- backspace -> bewegt den Cursor eine Spalte nach links
- zeichen ->zeichnet das zeichen an die Stelle des Cursors und schiebt den cursor nach rechts

