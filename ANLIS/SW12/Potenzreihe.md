## Definition
Eine **Potenzreihe** in **Potenzen von** ($x-x_{0}$) ist eine [[Reihen|Reihe]] der Form:
$$
\sum_{k=0}^{\infty}a_{k}(x-x_{0})^{k}= (a_{0}+a_{1}(x-x_{0})+a_{2}(x-x_{0})^2+a_{3}(x-x_{0})^{3}+\dots)
$$
Hier sind die $a_{k}$ $(k=0,1,\dots)$ die **Koeffizienten**, $x_{0}$ der **Entwicklungspunkt** und $x$ die **Variable** der Potenzreihe.

### Beispiel:
Die Reihe $\sum_{k=0}^{\infty}x^{k}=1+x+x^{2}+x^{3}+\dots$ ist eine Potenzreihe mit dem Koeffizienten $a_{k}=1,\forall k$ und dem Entwicklungspunkt $x_{0}=0$. Die Variable ist hier $x$.


## Konvergenz
Die Potenzreihe konvergiert sicher für $x=x_{0}$!
>[!info]
>Für jede Potenzreihe:
>$$\sum_{k=0}^{\infty}a_{k}(x-x_{0})^{k}=(a_{0}+a_{1}(x-x_{0})+a_{2}(x-x_{0})^2+a_{3}(x-x_{0})^{3}+\dots)$$
>git es eine reelle $R\geq 0$, genannt **Konvergenzradius**, so dass die Potenzreihe konvergiert, falls $\lvert x-x_{0} \rvert \lt R$ und divergiert, falls $\lvert x-x_{0} \rvert \gt R$ (für $\lvert x-x_{0} \rvert = R$ kann die Reihe entweder konvergieren oder divergieren). Dabei gilt:
>$$R=\lim_{ n \to \infty } \left\lvert  \frac{a_{k}}{a_{k+1}}  \right\rvert, \space\space\space\space \text{bzw.} \space\space\space R=(\lim_{ k \to \infty } \sqrt[k]{ \lvert a_{k} \rvert  })^{-1}$$
>,falls einer dieser Grenzwerte existiert oder beide existieren.

### Beispiel
**Potenzreihe**
$$
\sum_{k=0}^{\infty} \frac{x^{k}}{3^{k}}=1+\frac{x}{3}+\frac{x^{2}}{3^{2}}+\frac{x^{3}}{3^{3}}+\frac{x^{4}}{3^{4}}+\dots
$$
1. Bildungsgesetz:
$$
a_{n}=3^{-n}\cdot x^n
$$
2. Nun:
$$
a_{k}=3^{-k}
$$
3. Einsetzen:
	Einserseits:
$$
\begin{align}
R&=\left(\lim_{ k \to \infty } \sqrt[k]{ \lvert a_{k} \rvert  }\right)^{-1} \\
R&=\left(\lim_{ k \to \infty } \sqrt[k]{ \lvert 3^{-k} \rvert  }\right)^{-1} \\
R&=\left(\lim_{ k \to \infty } \sqrt[k]{ 3^{-k}}\right)^{-1} \\
R&=\left(\lim_{ k \to \infty } 3^{\frac{-k}{k}}\right)^{-1} \\
R&=\left(\lim_{ k \to \infty } 3^{-1}\right)^{-1} \\
R&=\left( \frac{1}{3}\right)^{-1} \\
R&=3
\end{align}
$$
	Andererseits:
	$$
	\begin{align}
R&=\lim_{ k \to \infty }\left\lvert\frac{a_{-k}}{a_{k+1}}\right\rvert \\
R&=\lim_{ k \to \infty }\left\lvert\frac{3^{-k}}{3^{-(k+1)}}\right\rvert \\
R&=\lim_{ k \to \infty }\left\lvert\frac{3^{-k}}{3^{-k-1)}}\right\rvert   \\
R&=\lim_{ k \to \infty }\left\lvert\frac{3^{-k}}{3^{-k}\cdot 3^{-1}}\right\rvert \\
R&=\lim_{ k \to \infty }\left\lvert\frac{1}{1\cdot3^{-1}}\right\rvert \\
R&=\lim_{ k \to \infty }\left\lvert3\right\rvert \\
R&=3
\end{align}
$$
4. Der Entwicklungspunkt $x_{0}$ ist bei dieser Reihe $0$ und somit konvergiert die Reihe da: $\lvert x_{0} \rvert\gt R \implies \lvert 0 \rvert\gt 3$ .