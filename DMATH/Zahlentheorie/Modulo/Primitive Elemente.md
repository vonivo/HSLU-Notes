>[!Definition]
>Sei $p$ eine [[Primzahl]]. Ein Elemente $z\in\mathbb{Z}_{p}^{*}$ heisst **primitives Element** von $\mathbb{Z}_{p}^{*}$ falls, jedes Element $a\in\mathbb{Z}_{p}^{*}$ eine Potenz von $z$ ist. In diesem Fall lassen sich alle Elemente in $\mathbb{Z}_{p}^{*}$ "erzeugen", indem man $z$ immer wieder mit sich selber multipliziert.

**Beispiel**
Finde die Erzeugende Elemente in $\mathbb{Z}_{5}^{*}$:
$$
\begin{align}
4^{2}&\equiv1\text{ mod 5} \\
4^{3}&\equiv{4}\text{ mod 5} \\
4^{4}&\equiv{1}\text{ mod 5} \\
 \\
3^{2}&\equiv{4}\text{ mod 5} \\ 
3^{3}&\equiv{2}\text{ mod 5} \\
3^{4}&\equiv{1}\text{ mod 5}  \\
3^{5}&\equiv{3}\text{ mod 5}  \\
 \\
2^{2}&\equiv{4}\text{ mod 5}  \\
2^{3}&\equiv{3}\text{ mod 5} \\
2^{4}&\equiv{1}\text{ mod 5}  \\
2^{5}&\equiv{2}\text{ mod 5}
\end{align}
$$
=> Die erzeugenden Elemente sind $2$ und $3$.