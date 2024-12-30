>[!Definition]
>Sei $n\geq 2$. Wir führen auf der [[Menge]] $\mathbb{Z}_{n}={1,2,3,..n-1}$ eine Addition $\oplus_{n}$ (Addition modulo $n$) und eine Multiplikation $\odot_{n}$ (Multiplikation modulo $n$) ein. Für $a,b\in \mathbb{Z}$ sei:
>$$
>\begin{align}
a\oplus b&=a+b \text{ mod }n &=R_{n}(a+b) \\
a\odot b&=a\cdot b \text{ mod }n &=R_{n}(a\cdot b)
\end{align}
>$$

## Rechenregeln
>[!Theorem]
>Sei $n\geq 2$ und $a,b,c\in\mathbb{Z}_{n}=\{ 0,1,2,\dots ,n-1 \}$, dann gilt:
>$$
>\begin{align}
a\oplus_{n} b&=b\oplus_{n} a &\implies \text{Kommutativgesetz bei der Addition}\\
a\oplus_{n}0&=a &\implies \text{Neutralelement bei der Addition}\\
a\odot_{n}b&=b\odot_{n}a &\implies \text{Kommutativgesetz bei der Multiplikation}\\
a\odot_{n}1&=a &\implies \text{Neutralelement bei der Addition}\\
a\odot_{n}(b\oplus_{n}c)&=(a\odot_{n}b) \oplus_{n} (a\odot_{n}c)&\implies \text{Distributionsgesetz}
\end{align}
>$$



**Beispiele:**
$$
\begin{array}{c|ccc} \oplus_3 & 0 & 1 & 2 \\ \hline 0 & 0 & 1 & 2 \\ 1 & 1 & 2 & 0 \\ 2 & 2 & 0 & 1 \\ \end{array}
$$
$$
\begin{array}{c|ccc} \odot_3 & 0 & 1 & 2 \\ \hline 0 & 0 & 0 & 0 \\ 1 & 0 & 1 & 2 \\ 2 & 0 & 2 & 1 \\ \end{array}
$$
