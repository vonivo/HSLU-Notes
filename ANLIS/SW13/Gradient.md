Die [[Reellwertige Funktion|reellwertige Funktion]] $f$ ist von zwei Variablen $x$ und $y$ abhängig.

Der **Gradient** von $f$ ist derjenige [[Vektoren|Vektor]], dessen Komponenten die [[Partielle Ableitung|partielle Ableitung]] von $f$ nach den einzelnen Variablen sind:
$$
\nabla f(x)=\begin{bmatrix}
f_{x}(x) \\
f_{y}(x)
\end{bmatrix}
$$
Oder aber
$$
\nabla f(x,y)=\begin{bmatrix}
f_{x}(x,y) \\
f_{y}(x,y)
\end{bmatrix}
$$

## Beispiel
Funktion $f(x,y)=3x^{2}y$
Gradient
$$
\begin{align}
\nabla f(x,y) &= \begin{bmatrix}
3(x^{2})'y \\
3x^{2}(y)'
\end{bmatrix} \\
&=\begin{bmatrix}
6xy \\
3x^{2}
\end{bmatrix}
\end{align}
$$
Am Punkt $(1,1)$ ergibt das:$\begin{bmatrix}6 \\3\end{bmatrix}$.

## Eigenschaften
Ist $f$ eine [[Stetigkeit|stetige]] [[ANLIS/SW01/Funktionen/Funktion]], d.h. insbesondere im Punkt $(x_{0},y_{0})$ [[Ableitung|differenzierbar]] mit dem Gradienten $\nabla f(x_{0},y_{0}\neq 0)$, dann 
- ist die Richtung des Gradienten $\nabla f(x_{0},y_{0}\neq 0)$
	- **senkrecht (orthogonal)** zu den [[Konturlinien]] von $f$ durch $(x_{0},y_{0})$, d. h. den Kurven mit $f(x_{0},y_{0})=f(x,y)$.
	- gleich der **Richtung der maximalen Zunahme von $f$**
- ist der Betrag des Gradienten $||\nabla f(x_{0},y_{0})||$
		- gleich der **maximalen Änderung von $f$** in diesem Punkt.
		- gross, wenn die [[Konturlinien]] nahe beieinander sind und klein, wenn sie weit auseinander liegen.
