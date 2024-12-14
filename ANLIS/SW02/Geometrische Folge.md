Die Geometrische Folge (GF) ist ein [[Reelle Zahlenfolgen|reelle Zahlenfolge]], bei welcher der Quotient $q$ zweier beliebiger aufeinanderfolgender Glieder $a_{n}$ und $a_{n+1}$ konstant ist:
$$
a_{n+1} = qa_{n},\space \space \space n=1,2,\dots
$$
## Bildungsgesetz
$$
a_{n} = q^{n-1}
$$

## Beispiel
Die Folge
$$
(a_{n}) = 1,2,4,8,18,\dots
$$
ist eine GF mit dem Rekursionsvorschrift $a_{n+1}=2a_{n}, n \in \mathbb{N}$, dem ersten Glied $a_{1}=1$ und dem Quotienten $q=2$. So ist $a_{3} = qa_{2}=2*2=4$. 
Das Bildungsgesetz wäre dann $a_{n}=2^{n-1}$

Eine FG ist eindeutig beschrieben durch zwei Grössen:
- entweder durch ein beliebiges Glied $a_{n}$ und den Quotienten $q$
- oder durch zwei beliebige Glieder $a_{n}$ und $a_{n+k}$.

## Summe der endlichen geometrischen Reihe
$$
S = \sum_{k=0}^{n-1}q^k
$$
Wenn nun $q\cdot S$ ausgeschrieben wird und danach die Differenz von $qS-S$ gezogen wird:
![[Summe_Gf.png]]
Da sich bei der Subtraktion fast alle Terme negieren bleibt noch $q^n-1$
$$
\begin{align}
qS-S &=qS-S \\ \\
(q-1)S&=q^n-1 \\
S &= \frac{q^n-1}{q-1}
\end{align}
$$
Nun hat man die **Summe der endlichen geometrischen Reihe**:
$$
a_{0}+a_{0}q+a_{0}q^2+\dots+a_{0}1^{n-1}=\sum_{k=0}^{n-1}a_{1}q^n=a_{1}\frac{(q^n-1)}{q-1}
$$
