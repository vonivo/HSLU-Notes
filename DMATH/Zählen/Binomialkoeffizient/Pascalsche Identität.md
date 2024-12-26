Das Konstruktionsprizipt des [[Binomialkoeffizient|Pascalsche Dreieck]]
![[Pasted image 20241226104619.png]]
liefert für $n>0, 0\leq k\leq n$ die Pascalsche Identität
$$
\begin{align}
\begin{pmatrix}
n+1 \\
k
\end{pmatrix}&=\begin{pmatrix}
n \\
k-1
\end{pmatrix} + \begin{pmatrix}
n \\
k
\end{pmatrix} \\
\frac{(n+1)!}{k!(n+1-k)!}&=\frac{n!}{(k-1)!(n-(k-1))!} + \frac{n!}{k!(n-k)! \\} \\
&=\frac{n!}{(k-1)!(n-k+1)!}+\frac{n!}{k!(n-k)!} \\
&=\frac{kn!}{k(k-1)!(n-k+1)!}+\frac{n!}{k!(n-k)!} \\
&=\frac{kn!}{k!(n-k+1)!}+\frac{(n-k+1)n!}{k!(n-k+1)(n-k)!} \\
&=\frac{kn!}{k!(n-k+1)!}+\frac{(n-k+1)n!}{k!(n-k+1)!} \\
&=\frac{kn!+(n-k+1)n!}{k!(n+1-k)!} \\
&=\frac{kn!+nn!-kn!+n!}{k!(n+1-k)!} \\
&=\frac{nn!+n!}{k!(n+1-k)!} \\
&=\frac{(n+1)n!}{k!(n+1-k)!} \\
&=\frac{(n+1)!}{k!(n+1-k)!}
\end{align}
$$
