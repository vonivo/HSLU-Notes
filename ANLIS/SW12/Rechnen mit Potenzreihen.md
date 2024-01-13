## Addition 
[[Potenzreihe|Potenzreihen]] lassen sich im **Konvergenzbereich** gliedweise addieren und subtrahieren.
### Beispiel
$$
\begin{align}
e^{ x } &= 1+x+\frac{x^{2}}{2!}+\frac{x^{3}}{3!}+\frac{x^{4}}{4!}+\dots \\
e^{ -x }&=1-x+\frac{x^{2}}{2!}-\frac{x^{3}}{3!}+\frac{x^{4}}{e!}+\dots 
\end{align}
$$
Gliedweise addieren:
$$
\begin{align}
e^{ x }+e^{ -x } &= 1+1+x+(-x)+\frac{x^{2}}{2!}+\frac{x^{2}}{2!}+\frac{x^{3}}{3!}+\left( -\frac{x^{3}}{3!} \right)+ \frac{x^{4}}{4!}+\frac{x^{4}}{4!}+\dots \\
&=2+0+\frac{2x^{2}}{2!}+0+\frac{2x^{4}}{4!}+\dots \\
&=2\left( 1+\frac{x^{2}}{2!}+\frac{x^{4}}{4!} +\dots\right) \\
\frac{1}{2}(e^{ x }+e^{ -x }) &= 1+\frac{x^{2}}{2!}+\frac{x^{4}}{4!} +\dots \\
\cosh x&= 1+\frac{x^{2}}{2!}+\frac{x^{4}}{4!} +\dots
\end{align}
$$


## [[Ableitung|Differenziation]] und [[Integration]]
[[Potenzreihe|Potenzreihen]] lassen sich im **Konvergenzbereich** gliedweise differenzieren und integrieren
### Beispiel:
Zeigen Sie dass die [[Potenzreihe]] von $\sin(x)$ gleich der Potenzreihe von $\cos x$ ist.
1. Potenzreihe von $\sin x$
$$
x-\frac{x^{3}}{3!}+\frac{x^{5}}{5!}-\frac{x^{7}}{7!}+\frac{x^{9}}{9!}+\dots
$$
2. Potenzreihe von $\cos x$
$$
1-\frac{x^{2}}{2!}+\frac{x^{4}}{4!}-\frac{x^{6}}{6!}+\frac{x^{8}}{8!}+\dots
$$
3. Gliedweise differenzieren:
$$
\begin{align}
(\sin x)' &= \left(x-\frac{x^{3}}{3!}+\frac{x^{5}}{5!}-\frac{x^{7}}{7!}+\frac{x^{9}}{9!}+\dots\right)' \\
&=(x)'-\left(\frac{x^{3}}{3!}\right)'+\left(\frac{x^{5}}{5!}\right)'-\left(\frac{x^{7}}{7!}\right)'+\left(\frac{x^{9}}{9!}\right)'+\dots \\
&= 1-\frac{3x^{2}}{3\cdot2\cdot1}+\frac{5x^{4}}{5\cdot 4 \cdot3 \cdot 2 \cdot1}-\frac{7x^{6}}{7\cdot 6 \cdot5\cdot 4 \cdot3 \cdot 2 \cdot1} \\
&= 1-\frac{3x^{2}}{3\cdot2\cdot1}+\frac{5x^{4}}{5\cdot 4 \cdot3 \cdot 2 \cdot1}-\frac{7x^{6}}{7\cdot 6 \cdot5\cdot 4 \cdot3 \cdot 2 \cdot1}+\frac{9x^{8}}{9\cdot 8 \cdot7\cdot 6 \cdot5\cdot 4 \cdot3 \cdot 2 \cdot1} \\
&= 1-\frac{x^{2}}{2\cdot1}+\frac{x^{4}}{4 \cdot3 \cdot 2 \cdot1}-\frac{x^{6}}{6 \cdot5\cdot 4 \cdot3 \cdot 2 \cdot1}+\frac{x^{8}}{8 \cdot7\cdot 6 \cdot5\cdot 4 \cdot3 \cdot 2 \cdot1} \\
&= 1-\frac{x^{2}}{2!}+\frac{x^{4}}{4 !}-\frac{x^{6}}{6 !}+\frac{x^{8}}{8!}
\end{align}
$$

