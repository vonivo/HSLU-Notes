Man nennt zwei [[Matrizen]] $A$ und $B$ ähnlich, falls es eine [[Invertierte Matrix|invertierbare]] Matrix $M$ gibt, sodass $B=M^{-1}AM$.

Sind $A$ und $B$ ähnliche Matrizen, dann habe sie dieselben [[Eigenwerte und Eigenvektoren|Eigenwerte]].

## Herleitung für M
| A | B |
| ---- | ---- |
| $A =V\Lambda V^{-1}$ | $B = W\Lambda W^{-1}$ |
| $V^{-1}A=\Lambda V^{-1}$ | $W^{-1}B = \Lambda W^{-1}$ |
| $V^{-1}AV=\Lambda$ | $W^{-1}B W = \Lambda$ |
$$
\begin{align}
V^{-1}AV &= W^{-1}BW \\
WV^{-1}AV&=BW \\
WV^{-1}AVW^{-1}&=B \\
\end{align}
$$
Daraus folgt nun, dass $WV^{-1} = M^{-1}$ und $VW^{-1} = M$.
$$
M^{-1}AM = B
$$
Sprich $M = VW^{-1}$.
