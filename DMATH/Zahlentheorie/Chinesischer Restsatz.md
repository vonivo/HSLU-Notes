Welche Zahlen $x$ ergeben bei der [[Division]] durch $5$ den Rest $3$, bei der Division durch $7$ den Rest $2$ und bei der Division durch $9$ den Rest $4$?

>[!Theorem]
>Seien $m_{1},m_{2},\dots m_{k} \in \mathbb{N}^{+}$ **paarweise [[Division|teilerfremde]]**, positive Zahlen und $m:=m_{1}\cdot m_{2}\cdot\dots \cdot m_{k}$. Dann besitzt das System von $k$ *simultane Kongruenz*.
>$$
\begin{align}
x&\equiv r_{1}\text{ (mod } m_{1}) \\
x&\equiv r_{2}\text{ (mod } m_{2}) \\
\vdots\\
x&\equiv r_{k}\text{ (mod } m_{k})
\end{align}
>$$
>eine **eindeutige Lösung $x \text{ (mod m)}$**.

Eine solche Gleichung kann wie folgt gelöst werden:
1. Wir definieren für alle $i=1,2,3,\dots,k$:
$$
M_{i}=\frac{m}{m_{i}}, \text{ wobei } m = m_1\cdot m_{2}\cdot\dots \cdot m_{k}
$$
2. Für $i=1,2,\dots ,k$ hat $M_{i}$ ein [[Modulare Inverse|moulares Inverse]] (berechne mit den [[Erweiterter Euklidischer Algorithmus]])$y_{i} \text{ mod }m_{i}$, d.h.
$$
M_{i}\cdot y_{i} \equiv 1 \text{ (mod }m_{i})
$$
3. Die simultane Lösung der Kongruenz ist dann:
$$
x =\sum_{i=0}^{k}r_{i}\cdot M_{i}\cdot y_{i}
$$

**Beispiel**
Bestimmen sie alle Lösungen $x$ des folgenden Systems von Kongruenzen:
$$
\begin{align}
x&\equiv-2\text{ (mod 5)} \implies x&\equiv_{3}\text{ (mod 5)}\\
x&\equiv2\text{ (mod 7)} \\
x&\equiv{4}\text{ (mod 9)}
\end{align}
$$
1. Bestimme $M_{i}$
$$
\begin{align}
M_{1} &= \frac{5\cdot 7\cdot 9}{5} &=63 \\
M_{2} &= \frac{5\cdot 7\cdot 9}{7} &=45 \\
M_{3} &= \frac{5\cdot 7\cdot 9}{9} &=35
\end{align}
$$
2. Bestimme das Modulare Inverse $y_{i}$ sodass $y_{i}M_{i} \equiv 1 \text{ mod }m_{i}$
$$
\begin{align}
y_{1} \cdot M_{1} &= y_{1}*63 &= 2\cdot{6}3 &\equiv 1 \text{ (mod 5)} &y_{1}=2 \\
y_{2} \cdot M_{2} &= y_{2}*49 &= 5\cdot 49 &\equiv 1 \text{ (mod 7)} &y_{2}=5 \\
y_{3} \cdot M_{3} &= y_3*35 &= 8\cdot 35 &\equiv 1 \text{ (mod 9)} &y_{2}=8
\end{align}
$$
3. Bestimme $x$
$$
\begin{align}
x&=\sum_{i=0}^{3}r_{i}\cdot M_{i}\cdot y_{i} \\
&=3*63*2+2*45*5+4*35*8 \\
&=1948 \\
&\equiv 58 \text{ mod m} \\
&\equiv 58 \text{ mod 315}
\end{align}
$$
