[[Kurve|Kurven]] der Form $y=f(x)$ liegen in **expliziter Form** (man spricht von einer [[ANLIS/SW01/Funktionen/Funktion]]) vor, d.h. man kann für jede $x$ den Funktionswert berechnen und damit die Kurve sofort zeichnen.

Liegen Kurven in der Form $F(x,y) = 0$ vor, spricht man von der **impliziten Form**. Oft ist eine Auflösung nach $y$ nicht möglich. Trotzdem will man $y'$ berechnen.

## Beispiel
Die Kurve für einen Kreis mit Zentrum $(0,0)$ und Radius $R$ lautet $x^2+y^2=R^2$.
Wenn diese Funktion nach $y$ aufgelöst wird, erhält man 2 Funktionen: Eine für den oberen Halbkreis $y=\sqrt{ R^2-x^2 }$ und eine für den unterenn Halbkreis $y = -\sqrt{ R^2-x^2 }$. 

## Vorgehen beim [[Ableitung|Ableiten]]von Kurven
1. Leite $F(x,y) = 0$ gliedweise nach $x$ ab, wobei man $y=y(x)$ als Funktion von $x$ betrachtet. Dabei muss dann die [[Kettenregel]] beachtet werden.
2. Löse entstandene Gleichung nach $y' = y'(x)$ auf.
### Beispiel 1
Kurve:
$$
\begin{align}
x^2+y^2 = R^2 \\
x^2+(y(x))^2=R^2
\end{align}
$$
Ableitung:
$$
\begin{align}
[x^2+(y(x))^2]'=[R^2]' \\
[x^2+(y(x))^2]' = 0 \\
2x+[(y(x))^2]' = 0 \\
2x+2y(x)y'(x) = 0 \\
2y(x)y'(x) = -2x \\
y'(x) = -\frac{2x}{2y(x)} \\
y'(x) = -\frac{x}{y(x)} 
\end{align}
$$

### Beispiel 2
Kurve:
$$
\begin{align}
(x-2)^2+(y-1)^2=5^2 \\
(x-2)^2+(y(x)-1)^2=5^2
\end{align}
$$
Ableitung:
$$
\begin{align}
[(x-2)^2+(y(x)-1)^2]'=[5^2]' \\
2(x-2)\cdot 1+[(y(x)-1)^2]'=0 \\
2(x-2)+2(y(x)-1)\cdot y'(x)=0 \\
2(y(x)-1)\cdot y'(x)=-2(x-2) \\
y'(x)=-\frac{x-2}{y(x)-1}
\end{align}
$$


