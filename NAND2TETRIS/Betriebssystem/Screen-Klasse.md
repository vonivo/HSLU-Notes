Unterstütz die Grafikausgabe auf dem Bildschirm.

**API**
```java
function void clearScreen();
function void setColor(boolean b);
function void drawPixel(int x, int y)
function drawLine(int x1, int y1, int x2, int y2);
function drawRectangle(int x1, int y1, int x2, int y2);
function drawCircle(int x, int y, int r);
```

## Vektor vs Bitmap
Eine Vektorgrafik wird durch Formengeschrieben, welche gut skaliert werden können. Eine Bitmap ist eine Block von Nullen und Einsen welcher nicht gut vergrössert werden kann.

**Vektorgrafik**
```
drawLine(3,0,11,0);
drawRectangle(3,1,9,5);
drawLine(12,1,12,2);
drawLine(10,3,11,3);
drawLine(4,6,8,6);
drawLine(0,7,12,7);
drawLine(1,8,11,8);
```
Kann einfach
- gespeichert
- übertragen
- skaliert
- in Bitmap umgewandelt
werden.

**Bitmap**
```
0001110100011101
1100111010101101
1100111001011101
0000000000011111
1111110000000000
....
```


## DrawPixel
```java
function drawPixel(int x, int y) {
	address = 32*y+x/16
	value = Memory.peek[16384 + address]
	set the(x%16)th bit of value to the current color
	do Memory.poke(adress, value)
}
```

## DrawLine
Die Herausforderung ist die Linie schnell zu zeichnen.
- `drawLine` wird durch eine Folge von `drawPixel`-Operationen implementiert.
- In jedem Schritt muss entschieden werden ob nach rechts oder nach oben gegangen wird.
![[Pasted image 20260620141943.png]]
1. `a` und `b` halten fest, wie oft man hoch bzw. rechts gegangen ist.
2. Zeichnen eine Pixel solange `a <= dx && b <= dy`
3. Entschiede in welche Richtung gegangen wird.
	- Um das zu entscheiden wird das Verhältniss von $\frac{dy}{dd}$ zu Nutze gemacht und mit dem Verhältnis von $\frac{b}{a}$ vergleichen. Wenn $\frac{b}{a}\geq \frac{dy}{dx}$ dann wird nach rechts gegangen, sonst nach oben.
	- Da die Ständige Berechnung ineffizient ist kann man das auch über eine Hiflsvariable machen `diff = a*dy-b*dx`. Jetzt wenn wir `a` erhöhen wird `diff` um `dy` erhöht und wenn wir `b` erhöhen wird `diff` um `dx` verkleiner. 
```java
a=0,b=0,diff=0
while((a<=dx) && (b<=dy)) {
	drawPixel(x+a,y+b)
	if (diff >0) {
		a++
		diff += dy
	} else {
		b++
		diff -=dx
	}
}
```

## DrawCircle
```java
foreach dy=-r to r do:
	drawLine(x-Math.sqrt(r^2-dy^2), y+dy ,x+Math.sqrt(r^2-dy^2), y+dy)
```
![[Pasted image 20260620143455.png|412]]
- Könnte zu einem Überlauf führen. `r` muss kleiner als 181 sein.