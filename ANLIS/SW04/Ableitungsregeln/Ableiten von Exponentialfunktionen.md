Die [[Exponentialfunktionen]] $\exp$ ist definiert durch die **Exponentialreihe**
$$
e^x=\exp x=\sum_{k=0}^\infty \frac{x^k}{k!}=1+x+\frac{x^2}{2}+\frac{x^3}{3!}+\dots, \text{ welche } \forall x \in \mathbb{R} \text{ konvergiert.}
$$
Man kann zeigen, dass
$$
\exp(x_{1}+x_{2}) =\exp(x_{1})\exp(x_{2})
$$ und 
$$
\lim_{ x \to 0 } \frac{\exp(x)-1}{x} = 1
$$
Also findet man für die Ableitung von der Exponentialfunktion
$$
\begin{align}
\frac{d}{dx}\exp x &= \lim_{\Delta x \to 0 } \frac{\exp (x +\Delta x)-\exp(x)}{\Delta x} \\
&=\lim_{ x \to 0 } \frac{\exp (x) \exp(\Delta x)-\exp(x)}{\Delta x} \\
&=\exp(x)\lim_{ x \to 0 } \frac{\exp(\Delta x)-1}{\Delta x} \\
&=\exp(x)\cdot 1 \\
&= \exp(x)
\end{align}
$$
>[!info]
>Die Funktion $e^x$ abgeleitet nach $x$ ist also wieder die Exponentialfunktion $e^x$.

