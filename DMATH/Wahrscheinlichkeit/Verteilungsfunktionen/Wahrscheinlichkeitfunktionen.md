Die **Wahrscheinlichkeitsfunktion** $f(x)$ der [[Hypergeometrisches Verteilung]] kann im Grenzfall grosser $N$ und $M$ und kleinem $n$ durch die [[Binomialverteilung]] $p=\frac{M}{N}$ approximiert werden.

 Die  [[Binomialverteilung]] kann für kleine $p$ und grosse $n$ durch die [[Poissonverteilung]] mit $\mu=np$ approximiert werden.

| Verteilung                                          | Parameter          | $f(k)$                                                                                                          | Bedinung für Approximation                                           |
| --------------------------------------------------- | ------------------ | --------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| [[Hypergeometrisches Verteilung\|hypergeometrisch]] | $N, M, n$          | $\frac{\begin{pmatrix}M\\k\end{pmatrix}\begin{pmatrix}N-M\\n-k\end{pmatrix}}{\begin{pmatrix}N\\n\end{pmatrix}}$ |                                                                      |
| [[Binomialverteilung\|binomial]]                    | $n, p=\frac{M}{n}$ | $\begin{pmatrix}n\\k\end{pmatrix}p^{k}(1-p)^{n-k}$                                                              | wobei $p=\frac{M}{n}$<br>$n\leq \frac{M}{10}, n\leq\frac{(N-M)}{10}$ |
| [[Poissonverteilung\|Poisson]]                      | $\mu=np$           | $\frac{\mu^{k}}{k!}e^{-\mu}$                                                                                    | wobei $\mu=np$<br>$p\leq 0.1, n\geq 100$                             |

