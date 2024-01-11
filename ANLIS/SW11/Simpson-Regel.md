Die Simpson Regel ist ein [[Numerische Integration|numerisches Integrations]]-Verfahren, bei welchen die Funktion $y=f(x)$ über $[x-\Delta x,a+\Delta x]$ durch eine [[Potenzfunktion|quadratische Funktion]] $P_{2}(x)=ax^2+bx+c$ approximiert.
$$
\int _{x-\Delta a}^{x+\Delta x}f(x) \, dx \approx \int _{x-\Delta x}^{x+\Delta x}P_{2}(x) \, dx  
$$
![[Simpson.png]]
wobei
$$
	\int _{a-\Delta x}^{x+\Delta x}P_{2}(x) \, dx =\int _{a-\Delta x}^{x+\Delta x}(ax^{2}+bx+c) \, dx = \left[ \frac{a}{3}x^{3}+\frac{b}{2}x^{2}+cx \right]_{x-\Delta x}^{x+\Delta x}
$$
Durch Umstellen erählt man:
$$
\begin{align}
\int _{a-\Delta x}^{x+\Delta x}P_{2}(x) \, dx&= \frac{a}{3}\left((x+\Delta x)^{3}-(x-\Delta x)^{3}\right) + \frac{b}{2}\left((x+\Delta x)^{2}-(x-\Delta x)^{2}\right)+\left(c(x+\Delta x)-(x-\Delta x)\right) \\
&= \frac{a}{3}(6x^{2}\Delta x+2(\Delta x)^{3})+\frac{b}{2}(4x\Delta x)+2c\Delta x
\end{align}
$$
Wenn wird verwende, dass folgendes gilt:
$$
\begin{align}
f(x-\Delta x)&=a(x-\Delta x)^{2}+b(x-\Delta x)+c \\
f(x)&=ax^{2}+bx+c \\
f(x+\Delta x)&=a(x+\Delta x)^{2}+b(x+\Delta x)+c
\end{align}
$$
finden wir $f(x-\Delta x) + 4f(x)+f(x+\Delta x)+f(x+\Delta x) = 6ax^2 +2a(\Delta x)^{2}+6bx+6c$ Und deshalb
$$
\int _{a-\Delta x}^{x+\Delta x}P_{2}(x) \, dx = \frac{\Delta x}{3}(f(x-\Delta x)+4f(x)+f(x+\Delta x))
$$
Dieses Resultat wird jetzt verwendet um das Integral $\int _{a}^{b}f(x) \, dx$ zu approximieren. Dazu unterteilen wir $[a,b]$ in eine **gerade Anzahl** $n=2k$ $(k\in \mathbb{N})$ gleich grosse Teilintervalle der Länge $\Delta x=\frac{b-a}{n}$ und verwenden über je zwei Teilintervalle die obige Approximation
$$
I = \int _{a}^{b}f(x) \, dx \approx \frac{b-a}{3n} (f_{0}+4f_{1}+2f_{2}+4f_{3}+\dots+2f_{n-2}+4f_{n-1}+f_{n}) = I_{S}(h)
$$
## Fehler
Der Fehler in der Simpsonregel ist $O(h^{4})$, genauer:
$$
\lvert \varepsilon_{S} \rvert = I-I_{S}(h)\leq \frac{(b-a)h^{4}}{180}\max_{\xi \in [a,b]}\lvert f^{(4)(x)} \rvert 
$$
