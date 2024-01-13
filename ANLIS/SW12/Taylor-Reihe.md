Falls wir $n$ gegen unendlich streben lassen, wird aus dem $n$-ten [[Taylor-Polynom]] $T_{n}(x)$ die **Taylor-Reihe**.

## Definition
Wir nehmen an, dass die Funktion $f:[a.b]\to \mathbb{R}, x \mapsto f(x)$ beliebig oft stetig differenzierbar ist. Dann ist die **Taylor-Reihe von $f$ an der Stelle $x_{0}$** definiert durch:
$$
\begin{align}
T(x) &= \sum_{k=0}^{\infty} \frac{f^{(k)}(x_{0})}{k!}(x-x_{0})^{k} \\
&=f(x_{0})+f'(x_{0})(x-x_{0})+\frac{f''(x_{0})}{2!}(x-x_{0})^{2}+\frac{f'''(x_{0})}{3!}(x-x_{0})^{3}+\dots
\end{align}
$$
Ist $x_{0} = 0$, nennt man $T(x)$ auch **Maclaurin-Reihe von $f$.

Die ersten zwei Terme ergeben die Lineare Approximation der Funktion an der Stelle $x_{0}$ bzw. $0$.

>[!info]
>Die Taylor-Reihe ist nichts anderes als eine [[Potenzreihe]] mit dem Entwicklungspunkt $x_{0}$. Es kann daher deshalb mit den bereits bekannten Methoden den [[Potenzreihe|Konvergenzradius]] $R$ bestimmt werden.

