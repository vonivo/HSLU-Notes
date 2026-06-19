>[!Definition]
>Ein Alphabet $\Sigma$ ist eine endliche Menge von Symbolen.
>Jedes Element $\sigma \in \Sigma$ ist ein **Zeichen** des Alphabets
>Jedes Element $\omega \in \Sigma^{*}$ wird als Wort über $\Sigma$ bezeichnet
>Jede Teilmenge $L \subseteq \Sigma^{*}$ ist eine formale Sprache über $\Sigma$

Sieh: [[AD/Formale Sprachen/Formale Sprache|Formale Sprache]]

Konkatenation: zweistellige Operation auf $\Sigma^{*}$.
$\Sigma^{*}$ entsteht aus $\Sigma$ druch Konkatenation von Worten.

**Definition $\Sigma^{*}$**
$$
\begin{align}
	\Sigma^{0} & := \{  \} \\
\Sigma^{1} & := \Sigma \\
	\Sigma^{n+1} & :=\{ xy|x \in \Sigma, y \in \Sigma^{n} \} \\
	\Sigma^{+} & :=U^{\infty}_{i=1}\Sigma^{i} \\
\Sigma^{*} & :=U^{\infty}_{i=0}\Sigma^{i}
\end{align}
$$
**Beispiel**
$$
\begin{align} \\
	\Sigma & := \{ a,b \} \\
	\Sigma^{0} & := \{  \} \\ 
    \Sigma^{1} & := \{ a,b \} \\
    \Sigma^{2} & := \{ a,b,aa,bb,ab,ba \} \\
\dots
\end{align}
$$

Eine Formale Sprache wird aus einer [[Formale Grammatik|Formalen Grammatik]] gebildet.


