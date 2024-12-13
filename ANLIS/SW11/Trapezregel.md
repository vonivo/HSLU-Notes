Unterteile das Intervall $[a,b]$ in $n$ gleich grosse Teilintervalle $[x_{j-1},x_{j}]$, $j=1,2,\dots ,n$.
In jedem Teilintervall approximiert man die Funktion $f$ durch eine [[Lineare Funktion|lineare Funktion]].![[Trapezregel.png]]
Das Integral über jedem Teilintervall wird approximiert durch die Trapezfläche.

Die Summe der Trapezfläche ist dann eine gute Approximation des bestimmten Integrals, vor allem wenn man $n$ genügend gross wählt. (Anstelle von Rechtecken wie beim [[Riemann Integral]] werden einfach Trapeze verwendet.)
$$
\int _{a}^{b}f(x) \, dx = \sum_{j=1}^{n} \frac{h}{2}(f(x_{j-1}+f(x))) \space\space\space \text{wobei}\space\space h=\frac{b-a}{n}
$$
Der bei der Trapezregel
$$
\int _{a}^{b}f(x) \, dx = \frac{b-a}{2n}(fx_{0}+2f(x_{1})+2f(x_{2})+\dots+2f(x_{n-1})+f(x_{n})) = I_{T}(h)
$$
gemachte Fehler $\varepsilon_{T}$ ist für gegenüber anständigen (z. B. stückweise [[Stetigkeit|steigen]]) [[ANLIS/SW01/Funktionen/Funktion|Funktionen]] $f$ beschränkt durch
$$
\lvert \varepsilon_{T} \rvert = \left\lvert  \int _{a}^{b}f(x) \, dx -I_{T}(h)  \right\rvert \leq \frac{(b-a)^{3}}{12n^{2}} \max_{\xi \in [a,b]}\lvert f''(\xi) \rvert 
$$

## Beispiel Fehler
Die Funktion $f(x)=x^{2}$ soll mit der Trapezregel auf 6 Nachkommastellen approximiert werden. Wie viele Teilintervalle $n$ sind nötig.
Integral:
$$
\int _{0}^{1}x^{2} \, dx 
$$
1. Ableitung
$$
\begin{align}
f(x) &= x^{2} \\
f'(x) &= 2x \\
f''(x)&=2
\end{align}
$$
2. $\varepsilon$ Bestimmen
Da $\varepsilon$ eine Umgebung ist und auf 6 Nachkommastellen genau sein sollt wählen wir $\varepsilon = 0.5\cdot 10^{-7}$ 
3. $\max_{\xi \in [a,b]}\lvert f''(\xi)$ bestimmen in diesem Fall $2$
4. Einsetzen und umformen
$$
\begin{align}
0.5\cdot 10^{-7} &= \frac{(b-a)^{3}}{12n^{2}}\max_{\xi \in [a,b]}\lvert f''(\xi) \rvert \\
0.5\cdot 10^{-7} &= \frac{(1-0)^{3}}{12n^{2}}\cdot{2} \\
0.5\cdot 10^{-7} &= \frac{(1)^{3}}{6n^{2}} \\
0.5\cdot 10^{-7} &= \frac{1}{6n^{2}} \\
n^{2}&= \frac{1}{6\cdot 0.5\cdot 10^{-7}} \\
 n^{2}&= \frac{10^{7}}{3} \\
n&=\sqrt{ \frac{10^{7}}{3} } \\
&=15.0195
\end{align}
$$
Das heisst sobald $n\gt 15$ ist der Fehler auf 6 Nachkommastellen genau.