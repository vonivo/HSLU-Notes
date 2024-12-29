>[!Theorem]
>Für beliebige [[Menge|Mengen]] $A$ und $B$ gilt:
>$$
>|A\cup B|=|A|+|B| +|A\cap B|
>$$
>(Siehe [[Einschluss- Ausschlussprinzip]])

**Beispiel**
Wie viele positive natürliche Zahlen nicht grösser als $1000$ sind durch $7$ oder $11$ teilbar?
$$
\begin{align}
A &= \{ \text{"Zahlen weleche durch 7 teilbar sind"} \} \\
|A|&=\left\lfloor  \frac{1000}{7}  \right\rfloor = 142 \\
B &= \{ \text{"Zahlen welche durch 11 teilbar sind"} \} \\
|B|&=\left\lfloor  \frac{1000}{11}  \right\rfloor =90 \\
A \cap B &= \{ \text{"Zahlen welche durch 11 und 7 teilbar sind"} \} \\
|A\cap B|&=\left\lfloor  \frac{1000}{7*11}  \right\rfloor =12  \\

\end{align}
$$
=> $142+90-12=220$ 

>[!Theorem]
>Falls $A_{1},A_{2},\dots ,A_{n}$ beliebige, endliche Mengen sind, dann gilt:
>$|A_{1}\cup A_{2}\cup\dots \cup A_{n}| = \sum_{1\leq i\leq n}|A_{i}|-\sum_{1\leq i\leq j\leq n}|A_{i}\cap A_{j}| + \sum_{1\leq i\leq j\leq k\leq n}|A_{i}\cap A_{j}\cap A_{k}|-\dots+(-1)^{n+1}|A_{1}\cap A_{2}\cap\dots \cap A_{n}|$

Das Erste Summenzeichen hat $\begin{pmatrix}n\\1\end{pmatrix}$ Summanden, das zweite $\begin{pmatrix}n\\2\end{pmatrix}$ und das dritte $\begin{pmatrix}n\\3\end{pmatrix}$ usw. bis zu $\begin{pmatrix}n\\n\end{pmatrix}$ Summanden.

