Die Steigung der [[Tangente]] an der Stelle $x_{0}$ entspricht der [[Ableitung]] oder dem [[Differenzenquotient]].
![[Differenzial.png]]
Also:
$$
f'(x_{0}) = \frac{dy}{dx}
$$
Die Symbole $dy$ und $dx$ nennt man **Differenziale**.
Das **Differenzial** von $f$ an der Stelle $x_{0}$ ist
$$
dy = f'(x_{0})dx
$$
Nun kann man $\Delta y$ approximativ so definieren:
$$
\Delta y\approx dy =f'(x_{0})dx
$$
Dabei wird die Approximation genauer je näher man an $x_{0}$ ist.

## Beispiel
Funktion:
$$
f(x) = x^2+e^{x-1}
$$
Ableitung:
$$
\frac{dy}{dx} = f'(x) = 2x+e^{x-1}
$$
Differential:
$$
\begin{align}
\frac{\Delta y}{\Delta x} \approx \frac{dy}{dx}&= 2x+e^{x-1} \\
\Delta y &= (2x+e^{x-1})\Delta x
\end{align}
$$
$x_{0} = 1$ und $\Delta x = 0.1$:
$$
\begin{align}
\Delta y &= (2\cdot1+e^{1-1})\cdot 0.1 \\
&= (2+e^{0})\cdot 0.1 \\
&= (2+1)\cdot 0.1  \\
&= 3\cdot 0.1 \\
\Delta y = 0.3
\end{align}
$$
$\implies$ Der approximierte Wert von $\Delta y$ liegt bei $0.3$ wobei der exakte bei $0.3152$ liegt.

## Berechnung des Fehlers
Mithilfe des Differenzials kann auch der Fehler gemessen werden. Die Formel für den elektrischen Widerstand ist $R =\frac{k}{r^2}$ wobei $k$ eine konstante ist und $r$ den Radius des Kabels. Wie Wirkt sich nun ein Messfehler von $5\%$ auf den Widerstand $R$ aus?

Dafür wird die **Formel $\text{Fehler} = \frac{dy}{f(x)}$** benötigt.

### Beispiel
Funktion
$$
f(x) = \frac{k}{x^2}
$$
Differential
$$
\begin{align}
\frac{dy}{dx} &= \left( \frac{k}{x^2} \right)' \\
&= -\frac{2kx}{x^4} \\
&=  -\frac{2k}{x^3}\\ 
dy&=-\frac{2k}{x^3}dx
\end{align}
$$
Fehler:
$$
\begin{align}
\text{Fehler} &= \frac{dy}{f(x)} \\
&= \frac{\left( -\frac{2k}{x^3} \right)\cdot dx}{\frac{k}{x^2}} \\
&= -\frac{2k\cdot dx}{x^3} \cdot \frac{x^2}{k} \\
&= -2 \frac{dx}{x}
\end{align}
$$
Nun haben wir den **Multiplikator** für den Fehler.
$\implies$ ein $5\%$ Messfehler beim Radius des Kabels ergibt einen $\lvert -2\cdot 5\% \rvert= 10\%$ Fehler im Widerstand.

## Rechenregeln für Differentiale
| Ableitungsregel | Regeln für Differentiale |
| ---- | ---- |
| $[c]'=0$ | $d[c] = 0$ |
| $[cf]'=cf'$ | $d[cf] =c \cdot df$ |
| $[f+g]' = f'+g'$ | $d[f+g] = df+dg$ |
| $[f\cdot g]' = f'g + fg'$ | $d[f\cdot g] =df \cdot g+f\cdot dg$ |
| $\left[ \frac{f}{g} \right]' = \frac{f'\cdot g-f\cdot g'}{g^2}$ | $d\left[ \frac{f}{g} \right]=\frac{df \cdot g-f \cdot dg}{g^2}$  |
