>[!Definition]
>Sei $m\in\mathbb{N}/{0}$. Dann nennt man zwei gerade Zahlen $a$ und $b$ **kongruent modulo** $m$, falls $m\mid(a-b)$ d.h. $a$ und $b$ **liegen ein Vielfaches von $m$ auseinander**. Man schreibt dann $a\equiv b \text{ mod } m$ und sagt "$a$ ist kongruent zu $b$ modulo $m$".

>[!Theorem]
>Seien $a,b\in \mathbb{Z}$ und $n\in \mathbb{Z}^{+}$, dann gilt:
>$$
>\begin{align}
a\equiv b (\text{ mod n}) &\Longleftrightarrow n|(a-b) \\
&\Longleftrightarrow \exists q\in\mathbb{Z}:a-b=q\cdot n \\
&\Longleftrightarrow \exists q\in\mathbb{Z}:a=b+q\cdot n
\end{align}
>$$


> 
## Beispiele
$$
\begin{align}
13&\equiv1\text{ mod } 4 \text{ denn } 4\mid(13-1) \\
13&\equiv1\text{ mod } 3 \text{ denn } 4\mid(13-1)  \\
13&\not\equiv\text{ mod } 4 \text{ denn } 4\not\mid(13-1)
\end{align}
$$


## Rechenregeln
- $a\equiv b\text{ mod }m \leftrightarrow a\text{ mod } m = b \text{ mod m}$
- $a\equiv b\text{ mod } m \leftrightarrow \exists k\in\mathbb{Z}(a=b+km)$
- Falls $a\equiv b\text{ mod }m$ und $c\equiv d\text{ mod }m$, dann gilt erstens $a+c\equiv b+c\text{ mod } m$ und zweitens $ac\equiv bd\text{ mod }m$.

### Beispiel
Berechne $4^{17}\text{ mod }5$:
$$
\begin{align}
4^{17}\text{ mod 5}&=4^{16}\cdot4\text{ mod 5} \\
&=(4^{2})^{8}\cdot 4\text{ mod }5 \\
&=16^{8}\cdot 4 \text{ mod }5 \\
&=((16\text{ mod 5})^{8} \cdot{4}) \text{ mod } 5 \\
&=1^{8} \cdot 4 \text{ mod }5 \\
&=4
\end{align}
$$




