Wir betrachten als erstes den Fall von zwei komplementären [[Menge|Mengen]] $B$ und $\bar{B}$ für die gilt: $B\cup \bar{B}=\Omega$ und $B\cap \bar{B}=\emptyset$

Gegeben:
- $B, \bar{B} \subset \Omega$ (vollständige Zerlegung)
- $p(B),p(\bar{B})>0$
- Ein Ereignis $A$ mit $p(A)>0$

Dann gilt der **Satz von Bayes**
$$
p(B|A)=\frac{p(A|B)p(B)}{p(A)}
$$
Mit dem [[Satz der Totalen Wahrscheinlichkeit]] gilt:
$$
p(B|A)=\frac{p(A|B)p(B)}{p(A|B)p(B)+p(A|\bar{B})p(\bar{B})}
$$

## Allgemeiner Fall
>[!Theorem]
>Voraussetzungen:
>- $B_{1},,\dots B_{k} \subset \Omega$ eine vollständige Zerlegung von $\Omega$.
>- $p(B_{i})>0 \forall i$
>- Ereignis $A$ mit $p(A)>0$
>Dann gilt für jedes $j$:
>$$
>p(B_{j}|A)=\frac{p(A|B_{j})p(B_{j})}{p(A)}=\frac{p(a|B_{j})p(B_{j})}{\sum_{i=i}^{k}p(A|B_{i})p(B_{i})}
>$$

## Beispiel
Eine bestimmte Krankheit kommt bei 0.5 % der Bevölkerung vo. Ein Test zu Auffindung der Krankheit führt bei 999 % (Sensitivität) der Krankheit zu einer positiven Testreaktion, aber auch bei 2 % der Gesunden. Wie gross  ist die Wahrscheinlichkeit, dass eine zufällige ausgewählte Person, deren Test positiv ist, die Krankheit wirklich hat?

Wir definieren folgenden Mengen:
$$
\begin{align}
K&=\text{"Menge aller Kranken Menschen"}  \implies B\\
\bar{K}&=\text{"Menge aller gesunden Menschen"} \implies \bar{B} \\
T+ &= \text{"Menge der Pers mit + Test"} \implies A\\
T-&=\text{"Menge der Pers mit - Test"}
\end{align}
$$
Wir wissen:
$$
\begin{align}
p(K)&=\frac{5}{1000} \\
p(\bar{K})&=\frac{995}{1000} \\
p(T+|K) &= \frac{99}{100} \\
p(T+|\bar{K})&= \frac{2}{100}
\end{align}
$$
Nun wenden wir den Satz von Bayes und den [[Satz der Totalen Wahrscheinlichkeit]] an:
$$
\begin{align}
p(B|A)&=\frac{p(A|B)p(B)}{P(A|B)p(B)+p(A|\bar{B})p(\bar{B})} \\
&=\frac{p(T+|K)p(K)}{p(T+|K)p(K)+p(T+|\bar{K})p(\bar{K})} \\
&=\frac{\left( \frac{99}{100}* \frac{5}{100} \right)}{\frac{99}{100} \frac{5}{1000} +\frac{2}{100} \frac{995}{10000} } \\
&=\frac{495}{2485} \\
&\approx {0}.2
\end{align}
$$


