Der Differentialquotient ist die Steigung der [[Tangente]] in einem bestimmten Punkt.

Den Differentialquotient erhält man, indem man beim [[Differenzenquotient]] der [[Sekante]] das $\Delta x$ gegen $0$ laufen lässt:
$$
\lim_{ \Delta x \to 0 } \frac{\Delta y}{\Delta x}=\lim_{ \Delta x \to 0 }\frac{f(x_{0}+\Delta x)-f(x_{0})}{\Delta x}
$$
Falls dieser Grenzwert existiert, hiesst $f$ an der Stelle $x_{0}$ **differenzierbar**. Man nennt diesen [[Grenzwert]] **(erste) Ableitung von $f$ an der Stelle $x_{0}$** und bezeichnet ihn mit 
$$
y'(x_{0}), f'(x_{0}) \text{ oder } \left.\frac{dy}{dx}\right|_{x=x_{0}} \text{ oder } \left. \frac{df}{dx} \right|_{x=x_{0}}
$$
Die [[Ableitung]] von $f$ an der Stelle $x_{0}$ entspricht als der Steigung der Tangente in $(x_{0}, f(x_{0}))$.

## Rechenbeispiel für den Differentialquotient
Die Funktion:
$$f(x) =x^2$$
Differenzenquotient:
$$
\begin{align}
m &= \frac{f(x_{0} + \Delta x)-f(x_{0})}{\Delta x} \\
&= \frac{(x_{0}+\Delta x)^2-x_{0}^2}{\Delta x_{0}} \\
&= \frac{\Delta x^2+2\Delta xx_{0}+x_{0}^2-x_{0}^2}{\Delta x} \\
&= \frac{\Delta x^2+2\Delta x x_{0}}{\Delta x} \\
&= \Delta x+2x_{0}
\end{align}
$$
Differentialquotient:
$$
\lim_{ \Delta x \to 0 } (\Delta x+2x_{0})=2x_{0}
$$
