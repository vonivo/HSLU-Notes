Die Kettenregel wird benötigt um [[ANLIS/SW01/Zusammengesetzte Funktionen|zZusammengesetzte Funktionen]] abzuleiten.
## 1. Form
Ist die (innere) [[ANLIS/SW01/Funktionen/Funktion]] $u=g(x)$ an der Stelle $x$ und die äussere Funktion $y=f(u)$ an der Stelle $u=g(x)$ differenzierbar, dann ist die zusammengesetzte Funktion $(f\circ g)(x) = f(g(x))$ an der Stelle $x$ differenzierbar.
$$
\frac{dy}{dx}=\frac{dy}{du}\cdot \frac{du}{dx} \text{ oder } \frac{d}{dx}[f(g(x))]=\frac{d}{du}[f(u)]_{u=g(x)}\cdot  \frac{d}{dx}[g(x)]
$$
## 2. Form
Ist die innere Funktion $g$ in $x$ und die äussere Funktion $f$ in $g(x)$ differenzierbar, dann ist die Zusammensetzung von $f\circ g$ differenzierbar in $x$ und es gilt:
$$
\frac{d}{dx}[f(g(x))]=(f\circ g)'(x)=f'(g(x))*g'(x)
$$
d. h. die Ableitung von $f(g(x))$ ist gleich der **Ableitung der äusseren Funktion ausgewertet an der Stelle der inneren Funktion**, $f'(g(x))$, **multipliziert mit der inneren Funktion,** $g(x)$.


## Beispiel
Funktionen:
$$
f(x) = (x^3+2x)^{37}
$$
$\implies f(u) = u^27$ und $g(x)=x^3+2x$
$$
\begin{align}
f'(x) =f'(u)\cdot g'(x)&=((x^3+2x))^{37}\cdot (x^3+2x)' \\
&=37(x^3+2x)^{36}\cdot(3x^2+2)
\end{align}
$$
