**Beispiel**
Wir veralgemeinern das folgende Resultat:
$$
\begin{align}
(x+y)^{3} &= x^{3}+3x^{2}y+3xy^{2}+y^{3} \\
&=\begin{pmatrix}
3 \\
0
\end{pmatrix}x^{3}y^{0}+\begin{pmatrix}
3 \\
1
\end{pmatrix}x^{2}y^{1}+\begin{pmatrix}
3 \\
2
\end{pmatrix}x^{1}y^{2}+\begin{pmatrix}
3 \\
3
\end{pmatrix}x^{0}y^{3} \\
&=\sum_{k=0}^{3}\begin{pmatrix}
3 \\
k
\end{pmatrix}x^{3-k}y^{k}
\end{align}
$$
>[!Theorem]
>Für $x,y \in\mathbb{R}$ (sogar in $\mathbb{C}$) und $n\in\mathbb{N}$ gilt:
>$$
>(x+y)^{n}=\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix}x^{n-k}y^{k} = \begin{pmatrix}
n \\
0
\end{pmatrix}x^{n-0}y^{0}+\begin{pmatrix}
n \\
1
\end{pmatrix}x^{n-1}y^{1}+\dots+\begin{pmatrix}
n \\
n-1
\end{pmatrix}x^{1}y^{n-1}+\begin{pmatrix}
n \\
n
\end{pmatrix}x^{0}y^{n}
>$$

## Folgerungen
### Corollary 1
$$
\begin{align}
\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix} &= 2^{n} \\
2^{n}&=(1+1)^{n} \\
&=\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix}1^{n-k}1^{k}
\end{align}
$$

### Corollary 2

$$
\begin{align}
\sum_{k=0}^{n}(-1)^{k}\begin{pmatrix}
n \\
k
\end{pmatrix} &= 0 \\
0&=(1-1)^{n} \\
&=\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix}1^{n-k}(-1)^{k} \\
&=\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix}(-1)^{k}
\end{align}
$$


### Corollary 3
$$
\begin{align}
\sum_{k=0}^{n}(2)^{k}\begin{pmatrix}
n \\
k
\end{pmatrix} &= 3^{n} \\
3^{n}&=(1+2)^{n} \\
&=\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix}1^{n-k}(2)^{k} \\
&=\sum_{k=0}^{n}\begin{pmatrix}
n \\
k
\end{pmatrix}(2)^{k}
\end{align}
$$