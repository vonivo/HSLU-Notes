>[!Definition]
>Eine Zufallsvariable $X$ ist eine Abbildung vom [[Zufallsexperiment|Stichprobenraum]] $S$ in die [[Menge]] der reellen Zahlen $\mathbb{R}$, wobei jedem Ergebnis $r\in S$ eine reelle Zahl $X(r)$ zugeorndet wird.

**Beispiel**
Eine faire Münze wird 3-Mal geworfen. Sei $X(r)$ die Anzahl Kopf (**Zufallsvariable**) des Ergebnisses $r$ bei der Durchführung des Versuchs Man hat:
$$
\begin{align}
X(KKK)&=3 \\
X(KKZ)=X(KZK)=X(ZKK)&=3 \\
X(ZZK)=X(ZKZ)=X(KZZ) &=3 \\
X(ZZZ)&=1
\end{align}
$$
Hier ist $S =\{ ZZZ, ZZK, ZKZ,KZZ,ZKK,KKZ,KZK,KKK \}$ mit $|S|=2^{3}=8$.

## Wahrscheinlichkeitsverteilung einer Zufallsvariable
>[!Definition]
>Die **Wahrscheinlichkeitsverteilung** (oder kurz Verteilung) einer Zufallsvariable $X$ auf einen Stichprobenraum $S$ ist die [[Menge]]
>$$
>\{ (r,p(X=r))|\forall r\in X(S) \}
>$$
>wobei $p(X=r)$ die Wahrscheinlichkeit dafür ist, dass die Zufallsvariable $X$ den Wert $r$ annimmt. Die Verteilung von $X$ wird üblicherweise dadurch spezifiziert, dass man $p(X=r), \forall r\in X(S)$ tabelliert.

**Beispiel**
Bestimme die Verteilung aus dem obigen Beispiel.

| r        | 0             | 1             | 2             | 3             |
| -------- | ------------- | ------------- | ------------- | ------------- |
| $p(X=r)$ | $\frac{1}{8}$ | $\frac{3}{8}$ | $\frac{3}{8}$ | $\frac{1}{8}$ |
>[!warning]
>Die Summe der Verteilung ist immer $1$. Also $\sum_{r\in X(S)}p(X=r) = 1$.

