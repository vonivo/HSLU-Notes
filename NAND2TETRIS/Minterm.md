>[!Definition]
>Ein Ausdruck $m(x,y,z)$ heisst **Minterm**, wenn er genau für eine Belegung den Wert 1 hat.

| x   | y   | z   |     | f(x,y,z) | Minterm                                 |
| --- | --- | --- | --- | -------- | --------------------------------------- |
| 0   | 0   | 0   |     | 0        | $m_{0}$                                 |
| 0   | 0   | 1   |     | 0        | $m_{1}$                                 |
| 0   | 1   | 0   |     | 1        | $m_{2} = \bar{0} \cdot 1 \cdot \bar{0}$ |
| 0   | 1   | 1   |     | 0        | $m_{3}$                                 |
| 1   | 0   | 0   |     | 1        | $m_{4}=1 \cdot \bar{0} \cdot \bar{0}$   |
| 1   | 0   | 1   |     | 0        | $m_{5}$                                 |
| 1   | 1   | 0   |     | 1        | $m_{6}= 1 \cdot 1 \cdot \bar{0}$        |
| 1   | 1   | 1   |     | 0        | $m_{7}$                                 |

Mithilfe von Mintermen kann eine [[Boolesche Funktion]] abgebildet werden:
**Beipsiel**
Obige boolsche Funktion kann wie folgt dargestellt werden:
$$
\begin{align}
f(x,y,z) &= m_{2} \cdot m_{4}\cdot m_{6} \\
 & = (\bar{x} \cdot y \cdot\bar{z}) + (x\cdot \bar{y} \cdot \bar{z})+(x\cdot y\cdot \bar{z})
\end{align}
$$

**Beispiel**
$$
\begin{align}
f(0,1,1) &= \bar{0} \cdot 1 \cdot \bar{0} +0 \cdot \bar{1} \cdot \bar{1} + 0 \cdot 1 \cdot \bar{1} &= 0 \\
f(0,1,0) & = \bar{0} \cdot 1 \cdot\bar{0} + 0\cdot \bar{1} \cdot \bar{0} + 0\cdot1\cdot 0 &= 1
\end{align}
$$
