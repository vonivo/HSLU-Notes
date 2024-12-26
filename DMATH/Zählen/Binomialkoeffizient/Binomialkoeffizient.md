>[!Definition]
>$$
>\begin{pmatrix}
\alpha \\
k
\end{pmatrix}=\begin{cases}
\frac{\alpha \cdot(\alpha-1)\dots(\alpha-k+1)}{k} &k>0\\
1, &k=0
\end{cases} \alpha \in \mathbb{R}, k\in \mathbb{N}
>$$

Anzahl der $r$-[[Kombinationen]] von $n$ Elementen fpr $n,r \in \mathbb{N}$:
$C(n,r) = \begin{pmatrix}n\\r\end{pmatrix}=$ Anzahl der r-elementigen Teilmengen einer n-elementigen Mengen.


## Pascalsches Dreieck
Das Pascalsche Dreieck sieht wie folgt aus
$$
\begin{array}{c}  
1  \\
1 \quad 1  \\
1 \quad 2 \quad 1  \\
1 \quad 3 \quad 3 \quad 1 \\
1 \quad 4 \quad 6 \quad 4 \quad 1  \\
1\quad 5\quad 10 \quad 10 \quad 5 \quad 1
\end{array}
$$

Mit dem Binomialkoeffizient:
$$
\begin{array}{c}  
\binom{0}{0}  \\[4pt]  
\binom{1}{0} \quad \binom{1}{1}  \\[4pt]  
\binom{2}{0} \quad \binom{2}{1} \quad \binom{2}{2} \\[4pt] 
\binom{3}{0} \quad \binom{3}{1} \quad \binom{3}{2} \quad \binom{3}{3} \\[4pt]  
\binom{4}{0} \quad \binom{4}{1} \quad \binom{4}{2} \quad \binom{4}{3} \quad \binom{4}{4} \\[4pt] 
\binom{5}{0} \quad \binom{5}{1} \quad \binom{5}{2} \quad \binom{5}{3} \quad \binom{5}{4} \quad \binom{5}{5} \end{array}
$$

- Wie man sieht, ist der das Dreieck **symmetrisch** in der Mittelsenkrechte.
- Aussen besteht das Dreieck nur aus $1$en.
- Inneres Element ist die Summe der links und rechts darüberliegenden Elemente.

## Symmetrie
Das Dreieck ist symmetrisch denn für $n \in \mathbb{N}$ und $0\leq k\leq n$ gilt:
$$
\begin{align}
\begin{pmatrix}
n \\
k
\end{pmatrix}&=\begin{pmatrix}
n \\
n-k
\end{pmatrix} \\
\frac{n!}{k!(n-k)!}&=\frac{n!}{(n-k)!(n-(n-k))!} \\
&=\frac{n!}{(n-k)!(n-n+k)!} \\
&=\frac{n!}{(n-k)!(k)!}
\end{align}
$$







