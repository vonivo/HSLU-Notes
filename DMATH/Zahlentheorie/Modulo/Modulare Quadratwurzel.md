>[!Definition]
>Sei $a\in\mathbb{Z}_{n}^{*}, n\geq 2$. Eine Lösung $x\in\mathbb{Z}_{n}^{*}$ (falls sie existiert) der Gleichung
>$$
>x^{2}=a\text{ mod }n \text{   bzw.   }x\odot_{n}x =a
>$$
>heisst modulare Quadratwurzuel von $a \text{ modulo }n$. In diesem Fall nennt man $a$ quadratischer Rest (**QR**) modulo $n$. Andernfalls heisst $a$ quadratischer Nichtrest (**NR**).
>Bezeichnung:$x=\sqrt{ a }\text{ mod }n$.

**Beispiel 1**
Berechne die modularen Quadratwurzeln in $\mathbb{Z}_{7}^{*}=\{ 1,2,3,4,5,6 \}$
$$
\begin{array}{c||cccccc}
x & 1 & 2 & 3 & 4 & 5 & 6 \\
\hline x^{2}=x\odot_{7}x & 1 & 4 & 2 & 2 & 4 & 1
\end{array}
$$
Und jetzt wird diese Tabelle erstellt:
$$
\begin{array}{c||cccccc}
a & 1 & 2 & 3 & 4 & 5 & 6 \\
\hline \sqrt{ a }\text{ mod 7}  & 1,6 & 3,4 & - & 2,5 & - & -
\end{array}
$$
**Beispiel 2**
Berechne die modularen Quadratwurzeln in $\mathbb{Z}_{15}^{*}=\{ 1,2,4,7,8,11,13,14 \}$
$$
\begin{array}{c||cccccccc}
x & 1 & 2 & 4 & 7 & 8 & 11 & 13 & 14 \\
\hline x^{2}=x\odot_{15}x & 1 & 4 & 1 & 4 & 4 & 1 & 4 & 1
\end{array}
$$
Und jetzt wird diese Tabelle erstellt:
$$
\begin{array}{c||cccccccc}
a & 1 & 2 & 4 & 7 & 8 & 11 & 13 & 14 \\
\hline \sqrt{ a }\text{ mod 15} & 1,4,11,14 & - & 2,7,8,13 & - & - & - & - & -
\end{array}
$$

- Falls $n=p$ ein [[Primzahl]] ist, so hat jedes Element in $\mathbb{Z}_{p}^{*}$ **keine** oder genau zwei Quadratwurzeln ($x$ und $p-x$).
- Falls $n=p\cdot q$ das Produkt von zwei verschiedenen Primzahlen ($p,q\neq 2$) ist, so hat jedes Element in $\mathbb{Z}_{n}^{*}$ entweder keine oder genau vier Quadratwurzeln, ($x,n-x,y,n-y$)
- Wegen der Symmetrie
$$
(p-x)^{2}=p^{2}-2px+x^{2}\equiv x^{2}\text{ mod }p
$$
genügt es die Zahlen $0<x\leq \left\lfloor  \frac{p}{2}  \right\rfloor$ zu untersuchen. Wenn also $x$ eine Quadratwurzel modulo $p$ ist, dann ist auch $p-x$ eine.

>[!Theorem]
>Sei $n=p\cdot q$ das Produkt zweier verschiedenen Primzahlen $p$ und $q$ (beide $\neq 2$). Dann ist das Berechnen von Quadratwurzeln modulo $n$ genau so schwierig, wie das Faktorisieren von $n$.

