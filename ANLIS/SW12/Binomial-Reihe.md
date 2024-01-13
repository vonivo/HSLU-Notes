Der **Binomische Lehrsatz** lautet für ein beliebiges $x \in \mathbb{R}$ und $n \in \mathbb{N}$
$$
(1+x)^{n}=\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix}x^{k}
$$
wobei $\begin{pmatrix}n\\k\end{pmatrix}= \frac{n!}{k!(n-k)}$ die **Binomialkoeffizienten** sind.

## Definition
Man nennt:
$$
(1+x)^{\alpha}=\sum_{k=0}^{\infty}\begin{pmatrix}
\alpha \\
k
\end{pmatrix}x^{k} \space\space\space\space\space\space mit \space\space\space\space\space\space \begin{pmatrix}
\alpha \\
k
\end{pmatrix} = \frac{\alpha \cdot(\alpha-1)\dots(\alpha-k+1)}{k\cdot(k-1)\dots 3 \cdot 2 \cdot 1}
$$
**Binomial-**[[Reihen|Reihe]]. Sie ist definiert für $\alpha \in \mathbb{R}$ und $\lvert x \rvert \lt 1$.

## Beispiel
Wie lautet die Binomial-Reihe von $\sqrt{ 1+x }$? Schreiben sie die ersten 4 Glieder auf.
1. Umformen:
$$
(1+x)^{\frac{1}{2}}
$$
2. Reihe:
$$
\begin{pmatrix}
\frac{1}{2} \\
0
\end{pmatrix}x^0 +\begin{pmatrix}
\frac{1}{2} \\
1
\end{pmatrix}x^{1} + \begin{pmatrix}
\frac{1}{2} \\
2
\end{pmatrix}x^{2}
$$
3. Koeffizient:
	1. $k=3$
	$$
\begin{align}
\begin{pmatrix}
\frac{1}{2} \\
3
\end{pmatrix}&= \frac{\frac{1}{2}\left( \frac{1}{2}-1 \right)\left( \frac{1}{2}-2 \right)}{3\cdot(3-1)(3-2)} \\
&=\frac{1}{16}
\end{align}
$$
	2. $k=2$
	 $$
	 \begin{align}
\begin{pmatrix}
\frac{1}{2} \\
2
\end{pmatrix}&= \frac{\frac{1}{2}\left( \frac{1}{2}-1 \right)}{2\cdot(2-1)}\\
&=-\frac{1}{8}
\end{align}
$$
	3. $k=1$
		 $$
	 \begin{align}
\begin{pmatrix}
\frac{1}{2} \\
1
\end{pmatrix}&= \frac{\frac{1}{2}}{1}\\
&=\frac{1}{2}
\end{align}
$$
	4. $k=0$
	$$
	 \begin{align}
\begin{pmatrix}
\frac{1}{2} \\
0
\end{pmatrix}&= 1
\end{align}
$$
4. Zusammensetzen
$$
1\cdot x^0+\frac{1}{2}\cdot x^1-\frac{1}{8}x^{2}+\frac{1}{16}x^{3}
$$
