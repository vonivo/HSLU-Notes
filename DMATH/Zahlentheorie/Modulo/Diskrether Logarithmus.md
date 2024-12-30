Sei $p$ stets eine [[Primzahl]] und $b\in\mathbb{Z}_{p}^{*}=\{ 1,2,3,..p-1 \}$.
>[!Definition]
>Die diskrete Exponentialfunktion zur Basis $b$ modulo $p$ ist definiert (und effizient berechenbar) durch:$$
>exp_{b}(k)=b^{k}\text{mod }p$$


>[!Definition]
>Unter dem Problem des diskreten Logarithmus versteht man:
>
>Finde zu gegebenem $y\in\mathbb{Z}_{p}^{*}$ ein $k\in\mathbb{N}$ (falls existent), sodass die folgende Gleichung erfüllt ist:
>$$
>y=b^{k}\text{ mod } p
>$$
>Man schreibt auch: $k=\log_{b}(y)\text{ mod p}$

Einfach: $k\to b^{k}\text{ mod }p$
Schwierig: $y\to \log_{b}(y)\text{ mod }p$

**Beispiel**
Finden sie eine Lösung $k$ der Gleichung $7=3^{k}\text{ mod }17$.
$k=\log_{3}(7)\text{ mod 7}$
$$
\begin{array}{c|ccccccccccc}
k & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 & 11 \\
\hline 3^{k}\text{ mod }17 & 3 & 9 & 10 & 13 & 5 & 15 & 11 & 16 & 14 & 8 & 7
\end{array}
$$
=> $k=7$


