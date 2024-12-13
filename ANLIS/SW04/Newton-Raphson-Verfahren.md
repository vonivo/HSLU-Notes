Das Newton-Raphson-Verfahren ist eine iterative Methode zur Bestimmung einer Nullstelle einer [[ANLIS/SW01/Funktionen/Funktion]]. Anders als bei der [[Regula Falsi]] wird nicht die [[Sekante]], sondern die [[Tangente]] verwendet.

![[Newton_Raphson.png]]
In einem ersten Schritt wird die Tangente an der Stelle $x_{0}$ gebildet. Danach wird die Nullstelle der Tangente berechnet, welche $x_{1}$ benannt wird.
In einem weiteren Schritt wird dann die Tangente an der Stelle $x_{1}$ bestimmt und wieder die Nullstelle gesucht.
Das wird wiederholt, bis man ein ausreichend genaues Resultat bekommen hat.

## Berechnung der Nullstelle der Tangente
Tangentengleichung:
$$
y = f(x_{0})+f'(x_{0})(x-x_{0})
$$
Nullstelle
$$
\begin{align}
0&=f(x_{0})-f'(x_{0})(x-x_{0}) \\
-f'(x_{0})(x-x_{0})&=f(x_{0}) \\
x-x_{0} &= -\frac{f(x_{0})}{f'(x_{0})} \\
x&=x_{0}-\frac{f(x_{0})}{f'(x_{0})}
\end{align}
$$


## Voraussetzungen
- $f(x)$ ist nicht [[Lineare Funktion|linear]]
- $f'(x)\ne0$
- Startwert $x_{0}$ ist nahe genug am gesuchten Wert (Gefahr, dass ansonsten divergiert oder oszilliert, und die richtige Nullstelle berechnet wird)
