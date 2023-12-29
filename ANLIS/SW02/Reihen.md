Im Gegensatz zu [[Reelle Zahlenfolgen|Folgen]] werden die Reihenglieder nicht mit einem '$,$', sondern einem '$+$' getrennt.
Zum Beispiel die Reihe, welchen den Dezimalbruch $\frac{1}{3}$ darstellt.
$$
\begin{align}
0.333\dots&=0.3+0.03+0.003+0.0003+\dots \\
&= 3(10^{-1}+10^{-2}+10^{-3}+10^{-4}+\dots) \\
&= 3\sum_{k=1}^{\infty}10^{-k}
\end{align}
$$
## Die [[Reelle Zahlenfolgen|Folge]] der $n$-ten Partialsumme
Auch aus Reihen kann man Summen erstellen, diese nennt man Partialsumme, wenn nicht alle Reihenglieder aufsummiert werden.
### Beispiel
Wir addieren nacheinander $2,3$ und $4$ Glieder der Reihe auf:
$$
\begin{align}{3}
0.33 &= 3(10^{-1} + 10^{-2}) &= \frac{33}{100} \\
0.333 &= 3(10^{-1} + 10^{-2}+10^{-3}) &=\frac{333}{1000} \\
0.3333 &= 3(10^{-1} + 10^{-2}+10^{-3}+10^{-4}) &=\frac{3333}{10000}
\end{align}
$$

## Summe einer Reihe
Die verschieden Summen bilden jetzt eine [[Geometrische Folge]] von welcher wir nun die Summe bestimmen können.
Nun bekommen wird folgende Summe:
$$
3\cdot10^{-1}\frac{(10^{-1})^n-1}{10^{-1}-1}
$$
Was passiert nun mit dieser Summe im Unendlichen $n \to \infty$?
$$
\begin{align}
\lim_{ n \to \infty } 0.33\dots3&=\frac{3\cdot10^{-1}}{10^{-1}-1}\lim_{ n \to \infty } ((10^{-1})^n-1) \\
&=\frac{3\cdot10^{-1}}{1-10^{-1}}\lim_{ n \to \infty } (1-(10^{-1})^n) \\
&=\frac{0.3}{0.9}(1-)\lim_{ n \to \infty } ((10^{-1})^n) \\
&=\frac{1}{3}(1-0) \\
&=\frac{1}{3}
\end{align}
$$


Falls die Folge der $n$-ten Partialsummen konvergiert,
$$
(s_{n})=\left( \sum_{k=1}^na_{k} \right)
$$
$$
s = \lim_{ n \to \infty } s_{n} = \lim_{ n \to \infty } \sum_{k=1}^na_{k}
$$
dann definiert man diesen [[Grenzwert einer Folge|Grenzwert]] (falls er existiert) als Summe der Reihe.
>[!info]
>$$
>\sum_{k=1}^na_{k}=\lim_{ n \to \infty }s_{n}=\lim_{ n \to \infty }\sum_{k=1}^na_{k}  
>$$


## Unendliche geometrische Reihe
Für die (unendliche) geometrische Reihe
$\sum_{k=0}^\infty a_{1}q^k$ ist die Folge der $n$-Partialsumme $(sn)=(a_{1}\frac{1-q^n}{1-q})$.
Für den Grenzwert dieser Folge findet man:
$$
s = \lim_{ n \to \infty }s_{n}=\lim_{ n \to \infty }a_{1}\frac{1-q^n}{1-q}=\frac{a_{1}}{1-q}\lim_{ n \to \infty } (1-q^n)  
$$
Nur für $|q|\lt1$ existiert $\lim_{ n \to \infty }q^n=0$. Also gilt:
>[!warning]
>$$
>a_{1}+a_{1}q+a_{1}q^2+a_{1}q^3+\dots=\sum_{k=0}^\infty a_{1}q^k=\frac{a_{1}}{1-q}, \text{falls} \lvert q \rvert\lt 1 
>$$


