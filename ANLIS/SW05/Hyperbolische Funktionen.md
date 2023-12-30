Die hyperbolischen Funktionen beinhalten den **Sinus hyperbolicus**, **Kosinus hyperbolicus** und **Tanges hyperbolicus**.

## Sinus- und Kosinus hyperbolicus

$$
\begin{align}
\sinh:\mathbb{R} \to \mathbb{R}, x \mapsto \sinh (x)&=\frac{1}{2}(e^x-e^{-x}) \\
\cosh:\mathbb{R}\to[1, \infty], x \mapsto \cosh(x) &= \frac{1}{2}(e^x+e^{-x})
\end{align}
$$
![[hyperbolicus.png]]
Dabei gelten die Beziehungen
$$
\begin{align}
\cosh^2(x)-\sinh^2 &=1 \\
\cosh(x+y)&=\sinh(x)\cosh(y)+\cosh(x)\sinh(x) \\
\cosh(x+y)&=\cosh(x)\cosh(y)-\sinh(x)\sinh (y)
\end{align}
$$

## Tangens hyperbolicus
Der **Tangens hyperbolicus** ist folgt definiert:
$$
\tanh:\mathbb{R}\to[-1,1], x \mapsto \tanh(x) = \frac{\sinh(x)}{\cosh (x)}=\frac{e^x-e^{-x}}{e^x+e^{-x}}
$$
![[tangenshyperbolicus.png]]
Der **Tanges hyperbolicus** kommt z. B. als Aktivierungsfunktion in künstlichen neuronalen Netzwerken vor.
