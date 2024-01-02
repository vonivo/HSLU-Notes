Um den Mittelpunkt des [[Krümmung|Krümmungskreises]] einer [[Kurve]] am Punkt $x$ bestimmen zu können, muss zuerst die [[Tangente]] an dieser Stelle berechnet werden.

Sobald der [[Ableiten einer Kurve|Tangentenvektor]] $\vec{t}(x)$ gefunden wurde, wird der [[Vektoren|Vektor]] $\vec{n}(x)$ bestimmt, welcher orthogonal zu dem Vektor $\vec{t}(x)$ liegt.
Der Vektor $\vec{n}(x)$ wird normiert und mit dem [[Krümmung|Krümmungsradius]] multipliziert.

Somit erhält man den Vektor zum Krümmungsmittelpunkt.

Kurve:
$$
\vec{x}(x) = \begin{bmatrix}
x, \\
y(x)
\end{bmatrix}
$$
Tangente:
$$
\begin{align}
\vec{t}(x) &= \begin{bmatrix}
(x)' \\
(y(x))'
\end{bmatrix} \\
&= \begin{bmatrix}
1 \\
y'(x)
\end{bmatrix}
\end{align}
$$
Normalenvektor:
$$
\vec{n}(x) = \begin{bmatrix}
-y'(x) \\
1
\end{bmatrix}
$$

Krümmungskradius:
$$
\frac{1}{K(x)}
$$
Mittelpunkt:
$$
\vec{x}_{M}(x) = \vec{x}(x)+\frac{1}{K(x)}\cdot \frac{\vec{n}(x)}{\lvert \vec{n}(x) \rvert }
$$
Oder direkt
$$
\vec{x}_{M} = \begin{bmatrix}
x_{m}(x) \\
y_{M}(x)
\end{bmatrix}=\begin{bmatrix}
x-y'(x) \frac{1+(y'(x))^2}{y''(x)} \\
y(x)+ \frac{1+(y'(x))^2}{y''(x)}
\end{bmatrix}
$$
