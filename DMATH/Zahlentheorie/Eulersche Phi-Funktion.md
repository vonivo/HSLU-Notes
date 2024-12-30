>[!Definition]
>Die Eulersche $\phi$-Funktion ist gegeben durch:
>$$
>\phi:\mathbb{N}\to \mathbb{N}, n \mapsto|\mathbb{Z}_{n}^{*}|=: \phi(n)
>$$
>sie ordnet jeder natürlichen Zahl $n$ die Anzahl der zu ihr teilerfremden natürlichen Zahl zu, die kleiner sind als $n$.

**Beispiel**
Bestimme $\phi(4), \phi(5),\phi(7),\phi({8})$: schreibe dazu $\mathbb{Z}_{i}^{*}$ für $i=4,5,6,7,8$ auf.
$$
\begin{align}
\phi(4)&=|\mathbb{Z}_{4}^{*}| =|\{ 1,3 \}| = 2 \\
\phi(5)&=|\mathbb{Z}_{5}^{*}| =|\{ 1,2,3,4 \}| = 4 \\
\phi(6)&=|\mathbb{Z}_{6}^{*}| =|\{ 1,5 \}| = 2 \\
\phi(7)&=|\mathbb{Z}_{7}^{*}| =|\{ 1,2,3,4,5,6 \}| = 6 \\
\phi(8)&=|\mathbb{Z}_{8}^{*}| =|\{ 1,3,5,6 \}| = 8
\end{align}
$$
>[!Theorem]
>Seien $p$ und $q$ zwei verschiedene Primzahlen, $m=p_{1}^{e_{1}}p_{2}^{e_{2}}\dots p_{r}e^{r}$ die Primfaktorzerlegung von $m\in\mathbb{N}$ und weiter $n\in\mathbb{N}$ [[ggT und kgV|teilerfremd]] zu $m$ ($ggT(m,n)=1$). Dann gilt:
>$$
>\begin{align}
\phi(p)&=p-1\\
\phi(p\cdot q)&=(p-1)(q-1)\\
\phi(m)&=(p_{1}-1)p_{1}^{e_{1}-1}(p_{2}-1)p_{2}^{e_{2}-1}\dots(p_{r}-1)p_{r}^{e_{r}-1}=m(1-\frac{1}{p_{1}})(1-\frac{1}{p_{2}})\dots(1-\frac{1}{p_{r}})\\
\phi(m\cdot n)&=\phi(m)\phi(n)
\end{align}
$$

**Beispiel**
$$
\begin{align}
\phi(6)&=\phi(2\cdot 3) &= (2-1)(3-1)&=2 \\
\phi(16)&=\phi(2^{4})&=16\left( 1-\frac{1}{8} \right)&=8 \\
\phi(693)&=\phi(3^{2}\cdot 7 \cdot{1}1)&=3^{2}\cdot 7 \cdot{1}1\left( 1-\frac{1}{3} \right)\left( 1-\frac{1}{7} \right)\left( 1-\frac{1}{11} \right)&=360 \\
\end{align}
$$



