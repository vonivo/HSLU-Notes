>[!Theorem]
>Für zwei beliebige Mengen $A$ und $B$ gilt $|A\cup B|=|A|+|B| - |A\cap B|$

## Beispiel
Wie viele Bits der Länge 8 starten mit einer $1$ oder enden mit den beiden Bits $00$?
$$
\begin{align}
A&=\text{"BS welche mit 1 starten"} \\
B&=\text{"BS welche mit 00 enden"}
\end{align}
$$
$$
\begin{align}
|A| &= 2^{7} &= 128 \\
|B| &= 2^{6} &= 64 \\
|A\cap B| &= 2^{8-3} &= 32
\end{align}
$$
=> Also ergibt das:$128+64-32=160$.