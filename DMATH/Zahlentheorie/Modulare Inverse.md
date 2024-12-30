>[!Definition]
>Die Modulare Inverse ist die Zahl $x^{-1}$ mit welcher sich die Zahl $x$ multiplizieren lässt, damit $x\cdot x^{-1}\text{ mod n }= 1$ ergibt.

**Beispiel**
$$
\begin{align}
x&=3 \\
x^{-1}&=2 \\
n&=5 \\
 \\
x\cdot x^{-1}\text{ mod } n &=1 \\
3\cdot{2}\text{ mod }5&=1
\end{align}
$$
=> $x\cdot x^{-1}\equiv1(\text{mod }n)$

Um das Modulare Inverse einer Zahl zu finden, kann die [[Diophantische Gleichung]] Gleichung verwendet werden:
$$
\begin{align}
n_{1}x+n_{2}y&=1 \\
n_{1}x&=1-n_{2}y \\
n_{1}x&\equiv 1 (\text{ mod }n_{2})
\end{align}
$$