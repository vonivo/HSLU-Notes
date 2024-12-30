>[!Definition]
>Existiert zu einem $a\in\mathbb{Z}_{n}$ mit $a\neq 0$ ein $b\in\mathbb{Z}_{n}$ mit $b\neq$ so dass $a\odot_{n}b=0$ gilt, so heisst $a$ ein **Nullteiler** von $\mathbb{Z}_{n}$.

- Nullteiler gibt es in $\mathbb{Z}$ oder $\mathbb{R}$ nicht
- Falls es in $\mathbb{Z}_{n}$ Nullteiler gibt, kann in $\mathbb{Z}_{n}$ **nicht** jede Gleichung $a\odot_{n}x=b$ gelöst werden.
**Beispiel:**
$$
\begin{array}{c|cccc}  
\odot_4 & 0 & 1 & 2 & 3  \\
\hline 0 & 0 & 0 & 0 & 0  \\
1 & 0 & 1 & 2 & 3 \\
2 & 0 & 2 & 0  & 2 \\
3 & 0 & 3 & 2 & 1
\end{array}
$$
$2\odot_{4}x=1$ -> Hat keine Lösung.

>[!Theorem]
>Sei $n=p$ eine [[Primzahl]]. Dann gilt:
>1. $\mathbb{Z}_{p}$ ist nullteilerfrei
>2. $\forall a,b\in \mathbb{Z}_{p}$ besitzt die Gleichung
>$$
>\begin{align}
a\odot_{p}x=b \text{   bzw.} \\
a\cdot x\equiv b \text{ mod }p
\end{align}
>$$
>genau eine Lösung $x(x=b\cdot a^{-1}=a^{-1}\cdot b)$.



