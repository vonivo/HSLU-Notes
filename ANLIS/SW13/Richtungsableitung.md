Die Änderungsrate wird **Richtungsableitung von $f$ im Punkt $x_{0}$ in Richtung $e$** genannt und bezeichnet mit:
$$
D_{e}f(x_{0}) = \lim_{ t \to 0+ } \frac{f(x_{0}+te)-f(x_{0})}{t} 
$$
![[Richtungsableitung.png]]
## Beispiel
### Beispiel 1
Berechne die Richtungsableitung von $f(x,y)=x+y$ im Punkt $x_{0}=[0,0]^{T}$ in die Richtung des Einheitsvektors $e=[\cos \psi, \sin \psi]^{T}$.

$$
x(t)=x_{0}+te = \begin{bmatrix}
0 \\
0
\end{bmatrix}+\begin{bmatrix}
t\cos \psi \\
t\sin \psi
\end{bmatrix}=\begin{bmatrix}
t\cos \psi \\
t\sin \psi
\end{bmatrix}
$$
Wert von $f$ bei $x(t):f(x(t))=x(t)+y(t)=t\cos \psi+t\sin \psi$
Änderungsrate von $f$, d. h. in Richtungsableitung von $f$:
$$
\begin{align}
D_{e}f(x_{0}) &= \lim_{ t \to 0+ } \frac{f(x(t),y(t))-f(x_{0},y_{0})}{t} \\
&= \lim_{ t \to 0+ } \frac{t\cos \psi+t\sin \psi}{t} \\
&=\lim_{ t \to t+ } \cos \psi+\sin \psi \\
&=\cos \psi +\sin \psi
\end{align}
$$
Für jeden Winkel $\psi$ können wir nun die Richtungsableitung in die Richtung $\psi$ berechnen. Dei [[Extrema]] sin bei $\psi=\frac{\pi}{4}, \frac{5\pi}{4}$, das Maximum ist bei $\psi=\frac{\pi}{4}$

### Beispiel 2
Bestimmen Sie die Richtungsableitung von $f(x,y,z) = 2x^{2}+3y^{3}+z^{2}$ an der Stelle $x_{0}=[2,1,3]^{T}$ in Richtung von $a=[1,0.-2]^{T}$. (Beachte: $\vec{a}$ ist **nicht normiert**)

Position zur Zeit $t$:
$$
\begin{align}
x(t)&=x_{0}+t\cdot a \\
&=\begin{bmatrix}
2 \\
1 \\
3
\end{bmatrix}+t\cdot \frac{1}{\sqrt{ 5 }} \begin{bmatrix}
1 \\
0 \\
-2
\end{bmatrix}
\end{align}
$$
Nun komponentenweise:
$$
\begin{align}
x&=2+\frac{t}{\sqrt{ 5 }} \\
y&=1 \\
z&=3-\frac{2t}{\sqrt{ 5 }}
\end{align}
$$

Wert von $f$ zur Zeit $t$:
$$
\begin{align}
\bar{f}(t)&=2(x(t))^{2}+3(y(t))^{3}+z(t)^{2} \\
&=2\left( 2+\frac{t}{\sqrt{ 5 }} \right)^{2}+3(1)^{3}+\left(3-\frac{2t}{\sqrt{ 5 }}\right)^{2} \\
\end{align}
$$
Änderungsrate der gewöhnliche [[Funktion]] $\bar{f}$ zur Zeit $t$:
$$
\begin{align}
D_{e}f(x_{0}) &= \lim_{ t \to 0+ } \frac{\bar{f}(t)-\bar{f}(x_{0})}{t}\\
&=\bar{f}'(0+) \\
&= \left[2\cdot2\left( 2+\frac{t}{\sqrt{ 5 }} \right)\cdot \frac{1}{\sqrt{ 5 }}+2\cdot\left(3-\frac{2t}{\sqrt{ 5 }}\right)\cdot-\frac{2}{\sqrt{ 5 }}\right]_{t=0} \\
&=-\frac{4}{\sqrt{ 5 }}
\end{align}
$$

## Richtungsableitung mit [[Einheitsvektoren]]
Für eine [[Stetigkeit|stetige Funktion]] kann die Richtungsableitung von $f$ im Punkt $x_{0}$ in Richtung des [[Einheitsvektoren]] $\vec{e}$ mithilfe des Gradienten bestimmt werden:
$$
D_{e}f(x_{0}) = \nabla f(x_{0})\cdot e=\lvert \nabla f(x_{0}) \rvert \cos \phi 
$$

### Beispiel
Gradient:
$$
\nabla f(x,y,z) = \begin{bmatrix}
f_{x}(x,y,z) \\
f_{y}(x,y,z) \\
f_{z}(x,y,z)
\end{bmatrix}=\begin{bmatrix}
4x \\
9y^{2} \\
2z
\end{bmatrix}
$$

 Im Punkt $x_{0} =[2,1,3]^{T}$ ist $\begin{bmatrix}8 \\9 \\6\end{bmatrix}$.
 Deshalb erhalten wir für die Ableitung in Richtung $e=\frac{1}{\sqrt{ 5 }}[1,0-2]^{T}$:
 $$
\begin{align}
D_{e}f(x_{0}) &= \nabla f(x_{0})\cdot e \\
&=\begin{bmatrix}
8 \\
9 \\
6
\end{bmatrix}\cdot \frac{1}{\sqrt{ 5 }}\begin{bmatrix}
1 \\
0 \\
-2
\end{bmatrix} \\
&=\frac{1}{\sqrt{ 5 }} (8\cdot 1+9\cdot 0 +6 \cdot (-2)) \\
&=\frac{1}{\sqrt{ 5 }} (8-12) \\
&=-\frac{4}{\sqrt{ 5 }}
\end{align}
$$
