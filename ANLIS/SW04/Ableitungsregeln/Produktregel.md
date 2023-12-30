Existieren die [[Ableitungen]] $u'(x)$ und $v'(x)$ dann gilt für die Ableitung des Produkts die Regel
$$
[u(x)\cdot v(X)]' = u'(x)\cdot v(x)+u(x)\cdot v'(x)
$$
auch geschrieben als
$$
\frac{d}{dx}[u(x)\cdot v(X)] = \frac{d}{dx}[u(x)]\cdot v(x)+u(x)\cdot \frac{d}{dx}[v'(x)]
$$
>[!info]
>Diese Regel kann und muss teilweise verkettet werden.
>Bsp: $[u(x)\cdot v(x)\cdot w(x)]' = [(u(x)\cdot v(x)) \cdot w(x)]'$

## Beispiel
$$
f(x) = (x^2-x+1)(x^3+x-1)
$$
$$
\begin{align}
f'(x) &= ((x^2-x+1)(x^3+x-1))' \\
&= (x^2-x+1)'(x^3+x-1) + (x^2-x+1)(x^3+x-1)' \\
&= (2x-1)(x^3+x-1) + (x^2-x+1)(3x^2+1) \\
&=2x^4+2x^2-2x-x^3-x+1+3x^4+x^2-3x^3-x+3x^2+1 \\
&=5x^4-4x^3+6x^2-4x+2
\end{align}
$$
