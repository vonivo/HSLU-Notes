Ein **Induktionsbeweis** wird verwendet um ein [[Prädikat]] (z.B. $P(n)$) beweisen. Dabei wird in folgender Reihenfolge vorgegangen:
1. **Induktionsverankerung**: Es wird gezeigt, dass $P(1)$ wahr ist.
2. **Induktionsschritt** Es wird gezeigt, dass die [[Implikation (Subjunktion)|Implikation]] $P(k)\to P(k+1)$ wahr ist $\forall k\geq 1$.
	1. **Induktionsvoraussetzung:** Annahme die Aussage $P(k)$ ist wahr für ein Bestimmtes $k\geq 1$
	2. **Induktionsbehauptung**. Die Aussage $P(k+1)$ ist wahr.
	3. **Induktionsbeweis**: Beweise, dass unter Annahme der **Induktionsvoraussetzung** die Induktionsbehauptung wahr ist.
	
>[!Kurzform]
>$[P(1)\land \forall k(P(k) \to P(k+1))\to \forall nP(n)]$

## Motivation
Sei $P(k)$ die Aussage "der $k$-te Dominostein fällt."
Wann fallen nun alle Dominosteine? Wann gilt $\forall nP(n)$?

1. **Induktionsverankerung**: Der erste Stein muss fallen, daher $P(1)$ = wahr.
2. **Induktionsschritt** Es wird gezeigt, dass die [[Implikation (Subjunktion)|Implikation]] $P(k)\to P(k+1)$ wahr ist $\forall k\geq 1$.
	1. **Induktionsvoraussetzung:** Annahme die Aussage $P(k)$ ist wahr für ein Bestimmtes $k\geq 1$
	2. **Induktionsbehauptung**. Falls der $k$-te Stein fäll, wird auch der $k+1$-te Stein fallen
	3. **Induktionsbeweis**: (Wird darauf verzichtet)
Solbad als der Stein $k=1$ fällt, fallen alle Steine.

## Beispiel
### Beispiel 1
**Beweise**: $\forall n\in\mathbb{N}\textbackslash\{0\} \left( 1+2+3+\dots+n=\frac{n(n+1)}{2} \right)$

1. **Induktionsverankerung**:
$$
\begin{align}
P(1) &= \frac{1(1+1)}{2} \\
&=1
\end{align}
$$
	$P(1)=1$ was wirklich auch der Summe von $1$ entspricht
2. **Induktionsschritt**
	1. **Induktionsvoraussetzung**: $P(k)$ ist wahr $\forall k\geq 1$.
	2. **Induktionsbehauptung**: falls $P(k)$ wahr ist $P(k+1)$ wahr für $\forall k\geq 1$
	3. **Induktionsbeweis**
$$
\begin{align}
1+2+3+\dots+n+(n+1)&\stackrel{?}{=}\frac{(n+1)((n+1)+1)}{2} \\
\frac{n(n+1)}{2}+(n+1)&\stackrel{?}{=}\frac{(n+1)(n+2)}{2} \\
\frac{n(n+1)}{2}+\frac{2n+2}{2}&\stackrel{?}{=}\frac{(n+1)(n+2)}{2} \\
\frac{n^{2}+n+2n+2}{2}&\stackrel{?}{=}\frac{(n+1)(n+2)}{2} \\
\frac{n^{2}+3n+2}{2}&\stackrel{?}{=}\frac{(n+1)(n+2)}{2} \\
\frac{(n+1)(n+2)}{2}&=\frac{(n+1)(n+2)}{2}
\end{align}
$$
=> Also $[P(1)\land \forall k(P(k)\to P(k+1))\to \forall nP(n)]$

### Beispiel 2
**Beweise**: $\forall n\in\mathbb{N}\textbackslash\{0\} \left( 7^{0}+7^{1}+\dots+7^{n-1}=\frac{7^{n}-1}{7-1} \right)$

1. **Induktionsverankerung**:
$$
\begin{align}
P(1) &= \frac{7^{1}-1}{7-1}  \\
&= \frac{7-1}{7-1} \\
&= \frac{6}{6}\\
&=1
\end{align}
$$

	$P(1)=1$ was wirklich auch der Summe von $1$ entspricht
2. **Induktionsschritt**
	1. **Induktionsvoraussetzung**: $P(k)$ ist wahr $\forall k\geq 1$.
	2. **Induktionsbehauptung**: falls $P(k)$ wahr ist $P(k+1)$ wahr für $\forall k\geq 1$
	3. **Induktionsbeweis**
$$
\begin{align}
7^{0}+7^{1}+\dots+7^{n-1} + 7^{n}&\stackrel{?}{=} \frac{7^{n+1}-1}{7-1} \\
\frac{7^{n}-1}{7-1}+7^{n}&\stackrel{?}{=} \frac{7^{n+1}-1}{7-1} \\
\frac{7^{n}-1}{7-1}+\frac{(7-1)7^{n}}{7-1}&\stackrel{?}{=} \frac{7^{n+1}-1}{7-1} \\
\frac{7^{n}-1}{7-1}+\frac{7^{n+1}-7^{n}}{7-1}&\stackrel{?}{=} \frac{7^{n+1}-1}{7-1} \\
\frac{7^{n}-1+7^{n+1}-7^{n}}{7-1}&\stackrel{?}{=} \frac{7^{n+1}-1}{7-1} \\
\frac{7^{n+1}-1}{7-1}&=\frac{7^{n+1}-1}{7-1}
\end{align}
$$

=> Also $[P(1)\land \forall k(P(k)\to P(k+1))\to \forall nP(n)]$