Ein [[Vektoren|Vektor]] kann auf verschiedenen Arten multipliziert werden.

## Skalarmultiplikation
Wird ein Vektor mit einem Skalar multipliziert, werden die einzelnen Komponenten eines Vektors mit dem Skalar multipliziert:
$$
\vec{a} = \begin{pmatrix}
a_{1} \\
a_{2} \\
a_{3}
\end{pmatrix}
$$
$$
3 *\vec{a} = 3\begin{pmatrix}
a_{1} \\
a_{2} \\
a_{3}
\end{pmatrix} =
\begin{pmatrix}
3 * a_{1} \\
3 * a_{2} \\
3 * a_{3}
\end{pmatrix}
$$
## Skalarprodukt
Werden zwei Vektoren miteinander multipliziert, entsteht daraus ein Skalar, das sogenannte Skalarprodukt.
$$
\vec{a} \bullet \vec{b} = c
$$
Das Skalarprodukt ist wie folgt definiert:
$$a\bullet b = a_{b} * |b| = |a| * b_{a} = |a| * |b| * \cos(\phi) = Skalarprodukt$$
Der Winkel $\phi$ definiert den Winkel zwischen zwei Vektoren. Und $a_b$ repräsentiert die Länge des Vektors $\vec{a}$ transponiert auf $\vec{b}$.


Das Skalarprodukt kann wie folgt berechnet werden:
$$\vec{a} = \begin{pmatrix}
a_{1} \\
a_{2} \\
a_{3}
\end{pmatrix}, \vec{b}=\begin{pmatrix}
b_{1} \\
b_{2} \\
b_{3}
\end{pmatrix}$$
$$
Skalarprodukt = a_{1} * b_{1} + a_{2} *b_{2} + a_{3} *b_{3}
$$
## Rechenregeln
### Kommutativgesetz
$$
a \bullet b = b \bullet a
$$
### Distributivgesetz
$$
(\vec{a} + \vec{b})\bullet \vec{c} = \vec{a} *\vec{c} + \vec{b}*\vec{c}
$$
### Gemischtes Assoziativgesetz
$$
(\lambda \circ \vec{a}) \bullet \vec{b} = \lambda * (\vec{a} \bullet \vec{b})
$$
