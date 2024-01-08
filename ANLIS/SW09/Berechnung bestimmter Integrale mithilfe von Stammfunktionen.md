Ein [[Bestimmtes Integral|bestimmtes Integral]] kann mithilfe von [[Integration|Stammfunktionen]] berechnet werden.
Durch den [[Fundamentalsatz der Differential- und Integralrechnung]] gilt:
$$
I(x) = \int _{a}^{x}f(t) \, dt = F(x)+C
$$
Wobei $F(x)$ eine **spezielle bekannte** Stammfunktion von $f(x)$ ist und $C$ eine geeignete reelle Konstante. Diese Konstante wird nun bestimmt:
$$
\begin{align}
I(a)= 0&= \int _{a}^{a}f(x) \, dx \\
&=F(a)+C \\
C&=-F(a)
\end{align}
$$
Somit gilt:
$$
I(x) = \int _{a}^{x}f(x) \, dx = F(x)-F(a) 
$$
und schließlich:
$$
\int _{a}^{b}f(x) \, dx = F(b)-F(a) 
$$
## Andere Stammfunktion
Eine andere Stammfunktion $F_{1}(x)$ unterscheidet sich von $F(x)$ durch eine additive Konstante $K \in \mathbb{R}$, d. h. $F_{1}(x)+K$
Wegen:
$$
\begin{align}
F_{1}(b)-F_{1}(a)&=(F(b)+K)-(F(a)+K) \\
 & =F(b)+K-F(a)-K \\
 & =F(b)-F(a)
\end{align}
$$

## Vorgehen
1. Irgendeine Stammfunktion $F(x)$ zum Integranden $f(x)$ bestimmen.
2. $F(a)$, $F(b)$ und $F(b)-F(a)$ berechnen und dann einsetzen in
$$
\int _{a}^{b}f(x) \, dx =[F(x)]_{a}^{b} = F(b)-F(a)
$$
## Beispiel
Funktion:
$$
f(x)=\sin x
$$
Integration:
$$
\int _{0}^{\pi}f(x) \, dx = \int _{0}^{\pi}\sin x \, dx 
$$
Stammfunktion:
$$
F(x) = -\cos x+C
$$
angewandt:
$$
\begin{align}
\int _{0}^{\pi}f(x) \, dx &= \left.F(x) \right|_{0}^{\pi} \\
 & =(-\cos x)|_{0}^{\pi} \\
 & =(-\cos \pi)-(-\cos0) \\
 & =(1) - (-1) \\
 & =2
\end{align}
$$