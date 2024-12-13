Die Frage ist, ob [[Taylor-Reihe]] einer [[ANLIS/SW01/Funktionen/Funktion]] **gleich** der [[ANLIS/SW01/Funktionen/Funktion]] ist ($T(x)=f(x)$)?

Genau dafür ist das Restglied nach Lagrange: Es ist gleich dem Fehler, den wir machen, wenn wir die [[ANLIS/SW01/Funktionen/Funktion]] $f$ durch das $n$-ten [[Taylor-Polynom]] ersetzen.

## Definition
Falls die [[ANLIS/SW01/Funktionen/Funktion]] $f:[a,b] \to \mathbb{R},x\mapsto f(x)$ mindestens $n+1$ mal stetig [[Ableitung|differenzierbar]] ist, dann gilt:
$$
f(x)=\sum_{k=0}^{n} \frac{f^{(k)}(x_{0})}{k!}(x-x_{0})+R_{n}(x)
$$
wobei das **Restglied nach Lagrange** gegeben ist durch:
$$
R_{n}(x)= \frac{\color{green}f^{(n+1)}(c)}{(n+1)!}{\color{red}(x-x_{0})}^{n+1}
$$
Wobei die grün markierte Stelle den Maximalwert von $f^{(n+1)}$ darstellt und die rot markierte stelle den Maximalwert von $f(x)$.

## Beispiel
Bestimme das $n$-te Restglied nach Lagrange für $f(x)=\sin x$, entwickelt an der Stelle $x_{0} = 0$.

1. Alle [[Ableitung|Ableitungen]] von $\sin x$ sind:
	1. $\pm \cos x$
	2. $\pm \sin xä
	Und somit ist der grüne maximalwert immer $-1$ oder $1$. $\implies \lvert f^{(n+1)}(c) \rvert \leq 1$.
2. Somit gilt:
$$
\begin{align}
\lvert R_{n}(x) \rvert &= \left\lvert  \frac{f^{(n+1)}(c)}{(n+1)!}(x-x_{0})^{n+1}  \right\rvert  \\
&\leq \frac{1}{(n+1)!}\lvert (x-0)\rvert ^{n+1}  \\
&\leq \frac{1}{(n+1)!}\lvert x\rvert ^{n+1} 
\end{align}
$$
Für ein festes $x$ muss nur $n$ genügend gross gewählt werden, damit $\lvert R_{n}(x) \rvert$ beliebig klein wird.


## Theorem
>[!info]
>Die [[Taylor-Reihe]] von $f$ an der Stelle $x_{0}$ konvergiert in ihrem Konvergenzbereich genau dann gegen $f(x)$, wenn das $n$-te Restglied nach Lagrange
>$$
>R_{n}(x)=f(x)-\sum_{k=0}^{n} \frac{f^{(k)}(x_{0})}{k!} \space \space\space \text{ für } n\to \infty \space \space \space \text{gegen } 0 \text{ konvergiert}.
>$$
>Wir schreiben dann $f(x)=\sum_{k=0}^{\infty} \frac{f^{(k)}(x_{0})}{k!}(x-x_{0}^{k})$

>[!info]
>Eine beliebig oft differenzierbare [[ANLIS/SW01/Funktionen/Funktion]] $f$ lässt sich in einer Umgebung $(x_{0}-R, x_{0}+R)$ von $x_{0}$ in eine konvergente [[Taylor-Reihe]] entwickeln, falls gilt:
>$$
>\lvert f^{(n)}(x) \rvert\leq KM^{n} \space\space\space \text{für alle } n \in \mathbb{N} \text{ und alle } x \in (x_{0}-R, x_{0}+R) 
>$$
>Dabei dürfen die Konstanten $K$ und $M$ nicht von $n$ und $x$ abhängen.




