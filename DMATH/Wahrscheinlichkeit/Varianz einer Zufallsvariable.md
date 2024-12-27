>[!Definition]
>Die **Varianz** der [[Zufallsvariable]] $X$ über dem [[Zufallsexperiment|Stichprobenraum]] $S$ ist definiert durch:
>$$
>V(X)=\sum_{s\in S}(X(s)-E(X))^{2} = \sum_{r\in X(s)}(r-E(X))^{2}p(X=R)
>$$
>Die **Standardabweichung** von $X$ ist definiert durch $\sigma(X)=\sqrt{ V(X) }$.

>[!Theorem]
Ist $X$ eine [[Zufallsvariable]], dann gilt $V(X)=E(X^{2})-[E(X)]^{2}$
=> $E(X^{2})=\sum_{r\in X(S)}r^{2}p(X=r)$

>[!Theorem]
>Sind $X$ und $Y$ zwei unabhängige Zufallsvariablen über dem Stichprobenraum $S$, dann gilt $V(X+Y)=V(X)+V(Y)$. Sind weiter $X_{i}, i=1,2,\dots n$ paarweise unabhängige Zufallsvariablen über $S$, dann gilt:
>$V(X_{1}+X_{2}+\dots+X_{n})=V(X_{1})+V(X_{2})+\dots+V(X_{n})$




**Beispiel**
Bestimmen Sie die Varianz (direkt mithilfe des Theorems) Zufallsvariable aus einem dreimaligen Münzwurf einer fairen Münze.

Zufallsvariable = Anzahl Kopf 

| r        | 0             | 1             | 2             | 3             |
| -------- | ------------- | ------------- | ------------- | ------------- |
| $p(X=r)$ | $\frac{1}{8}$ | $\frac{3}{8}$ | $\frac{3}{8}$ | $\frac{1}{8}$ |
Nun Berechnen wir den [[Erwartungswert]]:
$E(X)=0\cdot \frac{1}{8}+1\cdot \frac{3}{8}+2\cdot \frac{3}{8}+3\cdot \frac{1}{8}=\frac{12}{8}=1.5$

Und $E(X^{2})$
$E(X)=0^{2}\cdot \frac{1}{8}+1^{2}\cdot \frac{3}{8}+2^{2}+3^{2}\cdot \frac{1}{8}=\frac{24}{8}=3$

Nun wird die obere Tabelle erweitert:

| r              | 0             | 1             | 2             | 3             |
| -------------- | ------------- | ------------- | ------------- | ------------- |
| $p(X=r)$       | $\frac{1}{8}$ | $\frac{3}{8}$ | $\frac{3}{8}$ | $\frac{1}{8}$ |
| $(r-E(X))$     | $-1.5$        | $-0.5$        | $0.5$         | $1.5$         |
| $(r-E(X))^{2}$ | $2.25$        | $0.025$       | $0.025$       | $2.25$        |

$$
\begin{align}
V(X)&=\sum_{r\in X(S)}(r-E(X))^{2}p(X=r) \\
&=2.25\cdot \frac{{1}}{8}+ 0.025\cdot \frac{3}{8}+ 0.025\cdot \frac{3}{8} + 2.25\cdot \frac{1}{8} \\
&=\frac{1}{8}(2.25+0.75+0.75+2.25) \\
&=0.75
\end{align}
$$
Oder mithilfe des Theorems
$$
\begin{align}
V(X)&=E(X^{2})-[E(X)]^{2} \\
&=3-(1.5)^{2} \\
&=3-2.25 \\
&=0.75
\end{align}
$$

