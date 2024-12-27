>[!Definition]
>Der **Erwartungswert** einer [[Zufallsvariable]] $X(s)$ über dem [[Zufallsexperiment|Stichprobenraum]] $S$ ist gegeben durch:
>$$
>E(X)=\sum_{s\in S}X(S)\cdot p(s) = \sum_{r\in X(S)}r\cdot p(X=r).
>$$

## Rechenregeln
>[!Theorem]
>Falls $X_{i}, i=1,2,\dots,n$ Zufallsvariablen auf $S$ sind und $a,b$ beliebige reelle Zahlen, dann gilt:
>$$
>\begin{align}
(i)&E(X_{1}+X_{2}+\dots X_{n})&=E(X_{1})+E(X_{2})+\dots+E(X_{n}) \\
(ii)&E(aX+b)&=aE(X)+b
\end{align}
>$$




**Beispiel 1**
Bestimme den Erwartungswert der Zufallsvariable (Anzahl Kopf) bei einem 3-maligen Wurf mit einer fairen Münze.
*Zufallsvariable*

| r        | 0             | 1             | 2             | 3             |
| -------- | ------------- | ------------- | ------------- | ------------- |
| $p(X=r)$ | $\frac{1}{8}$ | $\frac{3}{8}$ | $\frac{3}{8}$ | $\frac{1}{8}$ |
$$
\begin{align}
E(X) &= \sum_{r\in X(S)}r\cdot p(X=r) \\
&=0\cdot \frac{1}{8}+1\cdot \frac{3}{8} + 2\cdot \frac{3}{8} + 3 \cdot \frac{1}{8} \\
&=\frac{12}{8}
\end{align}
$$
**Beispiel 2**
Wir Ziehen zufällig zwei Zahlen von $0$ bis $2$ (Wiederholungen erlaubt).
Wie ist die Verteilung der [[Zufallsvariable]] und wie sieht der Erwartungswert aus?
*Verteilung*
$$
\begin{align}
p(X=0)&=p(\{ 0,0 \})&= \frac{1}{9}\\ 
p(X=1)&=p(\{ 0,1 \},\{ 1,0 \})&= \frac{2}{9}\\
p(X=2)&=p(\{ 0,2 \},\{ 1,1 \},\{ 2,0 \})&= \frac{3}{9}\\
p(X=3)&=p(\{ 1,2 \},\{ 2,1 \})&= \frac{2}{9}\\
p(X=4)&=p(\{ 2,2 \})&= \frac{1}{9}
\end{align}
$$
*Erwartungswert*
$$
\begin{align}
E(X)&=\sum_{r\in X(S)}r\cdot p(X=r) \\
&=0\cdot \frac{1}{9}+1\cdot \frac{2}{9} + 2\cdot \frac{3}{9} +3 \cdot \frac{2}{9} + 4 \cdot \frac{1}{9} \\
&=\frac{18}{19}
\end{align}
$$


