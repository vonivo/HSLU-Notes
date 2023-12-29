Die Regula Falsi ist ein Verfahren zur Berechnung von Nullstellen.

Der Schnittpunkt der [[Sekante]] durch $(a, f(a))$ und $(b, f(b))$ mit der x-Achse ergibt die erste Näherung für die Nullstelle:
![[Regual_Falsi.png]]$$
x=a-f(a)\frac{b-a}{f(b)-f(a)}=\frac{af(b)-b(fa)}{f(b)-f(a)}
$$
Das erhaltene $x$ ist die nächste Näherung der Nullstelle. 
Nun muss überprüft werden ob $f(x) \cdot f(a) \lt 0$ ist.
- Wenn Ja:
	- Wird mit dem Intervall $[a,x]$ weitergefahren und $x$ wird zu $b$.
- Wenn nein:
	- Wird mit dem Intervall $[x,b]$ weitergefahren und $x$ wird zu $a$.

Nun wird der Prozess wiederholt und $x$ wird immer genauer.


## Herleitung
$$
\begin{align}
\frac{\Delta y}{\Delta x}=\frac{f(b)-f(a)}{b-a} &= \frac{f(x)-f(a)}{x-a} \\
x-a &= \frac{f(x)-f(a)}{f(b)-f(a)}(b-a) \\
x&=a+\frac{-f(a)}{f(b)-f(a)}(b-a) \\
&=\frac{a(f(b)-f(a))-f(a)}{f(b)-f(a)}(b-a) \\ \\
&=\frac{af(b)-af(a)-bf(a)+af(a)}{f(b)-f(a)} \\ \\
x&=\frac{af(b)-bf(a)}{f(b)-f(a)} \\
\end{align}
$$
Von der Zeile zwei auf Zeile drei fällt $f(x)$ weg, da wir die Nullstelle suchen, was heisst, dass $f(x) = 0, \forall x$.