>[!Theorem]
>Sei $p$ eine [[Primzahl]] und $m$ eine nicht negative ganze Zahl, dann gilt:
>$$
>m^{p} \text{ mod p } = m \text{ mod p}
>$$
>Daraus folgt falls $m<p$ gilt: $m^{p-1} \text{ mod }p = 1$.

## Beweisidee
- Induktionsverankerung: $m=0$: $0^{p} \text{ mod p} = 0$
- Induktionsschritt: Sei $m\geq 0$ und die Behauptung für $m$ wahr, d.h. es gelte $m^{p} \text{ mod } p = m \text{ mod }p$. Dann:
$$
\begin{align}
(m+1)^{p}&=\sum_{k=0}^{p}\begin{pmatrix}
p \\
k
\end{pmatrix}m^{p-k}\\
&=m^{p}+\begin{pmatrix}
p \\
1
\end{pmatrix}m^{p-1}+\begin{pmatrix}
p \\
2
\end{pmatrix}m^{p-2}+\dots+\begin{pmatrix}
p \\
p-1
\end{pmatrix}m+1
\end{align}
$$
Alle in der letzten Gleichung vorkommenden Binomialkoeffizienten sind durch $p$ teilbar, damit folgt:
$$
(m+1)^{p} \text{ mod }p=m^{p}+1 \text{ mod p} = m+1 \text{ mod }p
$$


