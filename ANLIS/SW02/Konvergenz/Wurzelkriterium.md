Das Wurzelkriterium ist ein [[Konvergenzkriterien|Konvergenzkriterium]], um die Art der Konvergenz zu ermitteln.

Ist $\sum_{k=0}^\infty a_{k}$ eine [[Reihen|Reihe]] und $p=\lim_{ k \to \infty }\sqrt[k]{ \lvert a_{k} \rvert }$, dann gilt:
- Falls $p\lt 1$, konvergiert die Reihe absolut,
- falls $p\gt1$ divergiert die Reihe absolut,
- falls $p=1$ kann die Reihe sowohl konvergieren als auch divergieren.

## Beispiel
Folge:
$$
(a_{k})=\frac{k}{5^k}
$$
Reihe:
$$
\sum_{k=0}^\infty \frac{k}{5^k}
$$
Vorgehen:
$$
\begin{align}
\sqrt[k]{a_{k}  }&=\sqrt[k]{ \frac{5}{5^k} } \\
 & =\frac{\sqrt[k]{ k }}{\sqrt[k]{ 5^k }} \\
 & =\frac{\sqrt[k]{ k }}{5} \\
\implies& \lim_{ k \to \infty } (\frac{\sqrt[k]{ k }}{5}) \\
&=\frac{\lim_{ k \to \infty } \sqrt[k]{ k }}{5} \\
&=\frac{1}{5}
\end{align}
$$
$\lim_{ k \to \infty }\sqrt[k]{ k } = 1$ siehe [[Grenzwert einer Folge]].
$\implies$ Die Reihe konvergiert absolut.