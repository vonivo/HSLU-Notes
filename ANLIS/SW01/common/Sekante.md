Eine Sekante ist eine Gerade, welche eine [[Funktion]] in zwei punkten Schneidet.
![[Differenzequotient.png]]
## Gleichung der Sekanten
Gegeben ist die Funktion $f:\mathbb{R} \to \mathbb{R}$ $x \mapsto f(x)=\frac{x^3}{4} +x +2$ und die Punkte $P(1,f(1))$ und $Q(2,f(2))$.

Nun wird zuerst die Steigung der Sekanten berechnet. Also den [[Differenzenquotient]]
$$
\begin{align}
m=\frac{f(2)-f(1)}{2-1}=\frac{ 2-\frac{11}{4} }{2-1}=-\frac{3}{4}
\end{align}
$$
Dann lautet die Gleichung der Sekanten mittels der [[Lineare Funktion|Gelichung für die Berechnung aus der Steigung und einem Punkt]] ermittelt werden
$$
\begin{align}
-\frac{3}{4} &= \frac{y-2}{x-2} \\
y&= -\frac{3}{4}x+\frac{7}{2}
\end{align}
$$
## Allgemeiner Fall
$$
m=\frac{f(x_{1}) - f(x_{0})}{x_{1}-x_{2}}
$$
Mit $\Delta x = x_{1}-x_{0}$ und $\Delta y = f(x_{1}-f(x_{0}))$ erhält man:
$$
m = \frac{f(x_{0}+\Delta x)-f(x_{0})}{\Delta x} = \frac{\Delta y}{\Delta x}
$$
und die Sekantengleichung lautet nun in Punkt-Richtugsform:
$$
m =\frac{y-y_{0}}{x-x_{0}}
$$