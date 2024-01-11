Die Approximierung der Bogenlänge der glatten ($f'$ ist stetig) [[Kurve]] $y=f(x)$ über dem Intervall $[a,b]$ durch die Länge eines Polygonzugs.
![[Bogenlänge_1.png]]
Dazu  unterteilen wir das Intervall $[a,b]$ in $n$ Teilintervalle durch Einfügen der Punkte $x_{1}x_{2},x_{3}$ bis $x_{n-1}$ zwischen $a=x_{0}$ und $b=x_{n}$

Länge des Polygonsements
$$
\begin{align}
\Delta l_{k} &= \sqrt{ (\Delta x_{k})^{2}+(\Delta y_{k})^{2} } \\
&= \Delta x \sqrt{ 1+\left[ \frac{\Delta y_{k}}{\Delta x} \right]^{2} }
\end{align}
$$
![[Bogenlänge_2.png]]
Für eine glatte Kurve gibt es einen Punkt $x_{k}^{*}$ zwischen $x_{k-1}$ und $x_{k}$ mit der Steigung der [[Sekante]]:
$$
f'(x_{k}^{*}) = \frac{f(x_{k})-f(x_{k-1})}{\Delta x_{k}} = \frac{\Delta y}{\Delta x}
$$
Also hat man
$$
\Delta l_{k}=\Delta x_{k}\sqrt{ 1+[f((x_{k}^{*}))]^{2} }
$$
![[Bogenlänge_3.png]]
wobei $x_{k-1}\leq x_{k}^{*}\leq x_{k}$. Summation ergibt die Länge des Polygonzugs
$$
\sum_{k=1}^{n}\Delta l_{k}=\sum_{k=1}^{n}\sqrt{ 1+[f'(x_{k}^{*})]^{2} }\cdot\Delta x_{k}
$$
Existiert der Grenzwert für $n \to \infty$ und $\max_{k} \Delta x_{k} \to 0$
$$
L = \lim_{ \max_{k}\Delta x_{k} \to 0 } \sum_{k=1}^{1}\sqrt{ 1+[f'(x_{k}^{*})]^{2} }\Delta x_{k}
$$
stellt die rechte Seite folgendes [[Riemann Integral|Riemansche Integral]] dar
$$
\int _{a}^{b}\sqrt{ 1+[f'(x)]^{2} } \, dx 
$$

>[!info]
>Is $y=f(x)$ eine glatte Kurve ($f'$ stetig) im Intervall $[a,b]$, dann ist die Länge dieser Kurve über $[a,b]$ gegeben durch
>$$
>L =\int _{a}^{b}\sqrt{ 1+[f'(x)]^{2} } \, dx = \int _{a}^{b}\sqrt{ 1+\left( \frac{dy}{dx} \right)^{2} } \, dx  
>$$

### Beispiel
Berechne die Bogenlänge der Kurve $y=x^{3/2}$ von $(1,1)$ nach $(2,2\sqrt{ 2 })$
1. Ableiten
$$
\begin{align}
f(x)&=x^{3/2} \\
f'(x)&=\frac{3}{2}\sqrt{ x }
\end{align}
$$
2. Einsetzen
$$
\begin{align}
\int _{1}^{2}\sqrt{ 1+[f'(x)]^{2} } \, dx \\
\int _{1}^{2}\sqrt{ 1+\left[{\color{red} \frac{3}{2}\sqrt{ x }} \right]^{2} } \, dx \\
\int _{1}^{2}\sqrt{ 1+\left[{\color{red} \frac{9}{4} x} \right] } \, dx \\
\int _{1}^{2}\sqrt{ \frac{1}{4}+ \frac{9x}{4} } \, dx \\ \\
\int _{1}^{2}\sqrt{\frac{4+9x}{4} } \, dx \\ \\
\int _{1}^{2}\frac{\sqrt{4+9x}}{2} \, dx \\ \\
\frac{1}{2}\int _{1}^{2}\sqrt{4+9x} \, dx \\
\end{align}
$$
3. Integrieren (Hier mit Hilfe der [[1. Substitutionsregel]])
$$
\begin{align}
u &= 4+9x \\
\frac{du}{dx}&=9 \\
du&=9dx \\
\frac{du}{9}&=dx
\end{align}
$$
$$
\begin{align}
&=\frac{1}{2}\int _{1}^{2}\sqrt{u} \frac{1}{9} \, du \\
&=\frac{1}{18}\int _{1}^{2}\sqrt{u} \, du \\
&=\frac{1}{18}\left[ \frac{2}{3}u^{3/2} \right]_{19}^{222} \\
&=\frac{1}{18}\left[ \frac{2}{3}22^{3/2} - \frac{2}{3}19^{3/2} \right] \\
&= \frac{1}{27}\left(\sqrt{ 22^{3} }-\sqrt{ 19^{3} }\right)
\end{align}
$$
## Kurven in Polarform
>[!info]
>$$
>L=\int _{\alpha}^{\beta}\sqrt{ (r(\phi))^{2}+(r'(\phi))^{2} } \, d\phi 
>$$

## Kurven in Parameterform
>[!info]
>$$
>L=\int _{a}^{b} \, ds=\int _{a}^{b}\lvert \dot{\vec{x}}(t) \rvert  \, dt = \int _{a}^{b}\sqrt{ (\dot{x}(t))^{2}+(\dot{y}(t)^{2}) } \, dt   
>$$


