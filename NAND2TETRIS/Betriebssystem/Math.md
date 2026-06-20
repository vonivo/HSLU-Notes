Die Math-Klasse implementiert mathematische Funktionen.

**API**
```java
function void init();
function int abs();
function int multiply();
function int divide();
function int min();
function int max();
function int sqrt();
```

## Multiply
```
multiply(x,y):
	sum = 0;
	for i = 0...y-1 do
		sum += x
	return sum;
```
Die Laufzeit dieser Implementation ist proportional zu der grösse von y.

Besser:
```
multiply(x,y):
	sum = 0;
	shiftedX = x
	for i = 0...n-1 do
		if((i'th bit of y) == 1)
			sum += shiftedX
		shiftedX *=2
	return sum;
```
Jetzt nur noch proportional zu der Anzahl Bits von y.

- Implementation des `i'th bit of y` mithilfe eines Arrays dass die 16 Werte von $2^{i}$ behinhaltet.


## Divide
```
divide(x,y):
	if (y>x) return 0
	
	q=divide(x, 2*y)
	if ((x-2*q*y) < y) 
		return 2*q
	else
		return 2*q+1
```
- Umgang mit negativen Zahlen durch $\frac{|x|}{|y|}$ und dannach die Vorzeichen richtig setzen.
- Überlaufbehandlung durch `if (y>x) or (y<0) return 0`.
## Sqrt
- Die Umkehrfunktion ($x^{2}$) kann leicht berechnet werden
- Die Umkehrfunktion ist monoton steigend
-> Quadratwurzeln können mit binärer Suche berechnet werden.
-> logarithmische Laufzeit

```
sqrt(x):
	y = 0
	for j = n/2....0 do
		if ((y+2^y)^2 <= x)
			y = y+2^j
	return y
```
Beispiel: 
$$
\begin{align}
\sqrt{ 125 } & =0*2^{4} \\
 & + 1*2^{3} \\
 & +0*2^{2} \\
&  +1*2^{1} \\
 & +1*2^{0} \\
 & = 8 + 2+1=11
\end{align}
$$
- Handelt es sich bei der Eingabe um einen Wert im zweierkomplement funktionier der Algorithmus auch mit negativen Zahlen.
- Der Algorithmus liefert immer die richtige Antwort in der moudlaren Arithmektik modulo $2^{16}$
- Überlaufbehandlung durch `if (y+2^j)^2 <= x && (y+2^j)^2 > 0`
