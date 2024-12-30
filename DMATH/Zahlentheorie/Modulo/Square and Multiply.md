Wie berechnet man effizient die modulare Potenz $5^{21}\text{ mod 11}$?

1. Der Exponent binär schreiben.
2. Eine $1$ wird zu $QM$ und eine $0$ zu $Q$
3. Streichen des ersten $QM$ (von Links)
4. $Q$ bedeutet quadrieren und $M$ multiplizieren. Nun wird die Basis anhand dieses Schemas mit sich selbst multipliziert oder quadriert. Wenn die Zahl zu gross wird, wird $\text{ mod } n$ gerechnet

**Beispiel**
1. 
$$
\begin{align}
21 &= (1'0101)_{2}
\end{align}
$$
2. $$
(1'0101) \implies QMQQMQQM
$$
3. $$
QMQQMQQM \implies QQMQQM
$$
4. $$
5\stackrel{Q}{\to}25\equiv3\stackrel{Q}{\to}9\stackrel{M}{\to}45\equiv1\stackrel{Q}{\to}1\stackrel{Q}{\to}1\stackrel{M}{\to}5
$$
