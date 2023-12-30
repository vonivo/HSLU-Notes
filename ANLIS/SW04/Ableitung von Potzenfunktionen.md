Für [[Ableitung]] von [[Potenzfunktion]] existiert folgende Regel:
$$
(x^n)' = nx^{n-1}
$$
Oder;
$$
\frac{d}{dx}(x^n)=nx^{n-1}
$$

## Herleitung
[[Differenzenquotient]] von $f(x)=x^n$ an der Stelle $x$ ist:
$$
\begin{align}
\frac{\Delta y}{\Delta x}&=\frac{f(x+\Delta x)-f(x)}{\Delta x}=\frac{(x+\Delta x)^n-x^n}{\Delta x} \\
&= \frac{1}{\Delta x} (x^n+nx^{n-1}\Delta x+\dots+\Delta x^n - x^n) \\
&= \frac{1}{\Delta x} (+nx^{n-1}\Delta x+\dots+\Delta x^n)  \\
&= (nx^{n-1}\Delta x^0+\dots+\Delta x^n) 
\end{align}
$$
nun wird der [[Differentialquotient]] gebildet:
$$
\lim_{ \Delta x \to 0 } (nx^{n-1}\Delta x^0+\dots+\Delta x^n)  = nx^{n-1}
$$
