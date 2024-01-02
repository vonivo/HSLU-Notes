Die logarithmische Differentiation hilft beim [[Ableitung|Ableiten]] von [[Funktion]] wie $f(x)=x^x$ (Form $f(x)=[u(x)]^{v(x)}$)

## Vorgehen
1. Auf beiden Seiten logarithmieren:
$$
\ln(f(x)) =v(x)\cdot \ln(u(x))
$$
2. Gleichsetzen mit $\frac{1}{f(x)}$
$$
v(x)\cdot\ln(u(x)) = \frac{1}{f(x)}
$$

4. Beide Seiten ableiten
$$
v'(x)\cdot \ln(u(x))+v(x)\cdot \frac{1}{u(x)} = \frac{f'(x)}{f(x)}
$$
5. Nach $f'(x)$ umstellen
$$
\left(v'(x)\cdot \ln(u(x)+\frac{v(x)}{u(x)}\right)\cdot f(x) = f'(x)
$$

## Beispiel
Funktion:
$$
f(x) =x^x
$$
1. Auf beiden Seiten logarithmieren:
$$
\ln(f(x)) = x\cdot \ln(x)
$$
2. Gleichsetzen mit $\frac{1}{f(x)}$
$$
x \cdot \ln(x) = \frac{1}{f(x)}
$$

4. Beide Seiten ableiten
$$
\ln(x) + x\cdot \frac{1}{x} = \frac{f'(x)}{f(x)}
$$
5. Nach $f'(x)$ umstellen
$$
\begin{align}
\ln(x)+x\cdot \frac{1}{x} &= \frac{f'(x)}{f(x)} \\
\ln(x)+1 &= \frac{f'(x)}{x^x} \\
(\ln(x)+1) x^x&= f'(x) \\
\end{align}
$$