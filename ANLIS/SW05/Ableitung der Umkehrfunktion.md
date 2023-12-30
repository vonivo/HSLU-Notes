Durch die Abbildung $f$ wird der Punkt $x$ auf $f(x)$ abgebildet. Durch die [[Umkehrfunktion|Umkehrabbildung]] $f^{-1}$ bildet diesen Punkt wieder auf $x$ ab, d. h. es gilt $f(f^{-1}(x)=Id(x) = x)$ oder $f^{-1}(f(x))=Id(x)=x$

Nun kann man mit Hilfe der [[Kettenregel]] und der Ursprungsfunktion $f(x)$ die [[Ableitung]] der [[Umkehrfunktion]] berechnen.

Dazu wird folgende Gleichung aufgestellt:
$$
f(f^{-1}(x)) = x
$$
Jetzt werden beide seiten der Gleichung nach $x$ abgeleitet:
$$
\begin{align}
(f(f^{-1}(x)))' &= (x)' \\
f'(f^{-1}(x))\cdot (f^{-1}(x))' &= 1 \\
(f^{-1}(x))' &=\frac{1}{f'(f^{-1}(x))}
\end{align}

$$
## Beispiel
Wir wollen die Funktion $\ln x$ ableiten. Nun benötigen wird die dazugehörige Umkehrfunktion.
Diese ist $e^x$.
Nun gilt:
$$
e^{\ln x}=x
$$
Nun wird abgeleitet:
$$
\begin{align}
(e^{\ln x})'&=(x)' \\
e^{\ln x}\cdot (\ln x)' &=1 \\
(\ln x)' = \frac{1}{e^{\ln x}}
\end{align}
$$
Nun kann der Term $e^{\ln x}$ rücksubstituiert werden und man erhält:
$$
(\ln x)'=\frac{1}{x}
$$
