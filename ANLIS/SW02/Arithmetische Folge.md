Die Arithmetische Folge ist eine [[Reelle Zahlenfolgen|reelle Zahlenfolge]] bei welcher die Differenz $d$ zweier beliebiger aufeinanderfolgender Glieder, $a_{n}$ und $a_{n+1}$ konstant ist.
$$
a_{n+1} = a_{n} + d, \space \space n=1,2,\dots
$$
## Beispiel
Die Folge
$$
(a_{n}) = 1,3,5,7,\dots
$$
ist eine AF mit dem Bildungsgesetz $a_{n}=2n-1, n \in \mathbb{N}$, dem ersten Glied $a_{1}=1$ und der Differenz $d=2$. So ist $a_{3} = a_{2}+2=3+2=5$.

Eine AF ist eindeutig beschrieben durch zwei Grössen:
- entweder durch ein beliebiges Glied $a_{n}$ und die Differenz $d$
- oder durch zwei beliebige Glieder $a_{n}$ und $a_{n+k}$

## Summe der AF
$$
\begin{align}
a_{1} + a_{2} + \dots+a_{n} &= \sum_{k=1}^na_{k} \\
\sum_{k=1}^nak &= \sum_{k=1}^n(a_{1}+(k-1)d) \\
&=\sum_{k=1}^na_{1} + d\sum_{k=1}^n(k-1) \\
&=na_{1} + d\frac{n(n-1)}{2} \\
&= \frac{n}{2}[a_{1}+\color{blue}a_{1}+(n-1)d] \\
&=\frac{n}{2}[a_{1}+\color{blue}a_{n}] \\
&= \frac{n(a_{1}+a_{n})}{2}
\end{align}
$$

