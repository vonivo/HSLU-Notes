## Allgemein
Der **Grenzwert** einer [[Funktion]] ist der Wert an einer bestimmten Stelle, dem sich die Funktion in der Umgebung der betrachteten Stelle annähert.

Dabei muss zwischen **linksseitigem Grenzwert** und **rechtsseitigem Grenzwert** unterschieden werden.
Die Sprungfunktion $f(x)=\frac{\lvert x \rvert}{x}=\left\{\begin{align}1, &x\gt 0\\-1, &x\lt 0\end{align}\right.$ hat zwei verschieden Grenzwerte.
![[Sprungfuntkion.png]]$$
\lim_{ x \to 0^+ } f(x)=\lim_{ x \to x^+ }\frac{\lvert x \rvert }{x}=\lim_{ x \to 0^+ } \frac{x}{x}=\lim_{ x \to 0^+ } \frac{1}{1}=1
$$
und
$$
\lim_{ x \to 0^- } f(x)=\lim_{ x \to x^- }\frac{\lvert x \rvert }{x}=\lim_{ x \to 0^- } \frac{-x}{x}=\lim_{ x \to 0^- } \frac{-1}{1}=-1
$$

Wohingegen die Funktion $f(x)=\frac{\sin x}{x}$ biede Grenzwerte gelich sind:
![[Pasted image 20231229142910.png]]$$
\lim_{ x \to 0^- } f(x)=1
$$
und
$$
\lim_{ x \to 0^+ }f(x)=1 
$$
Um diesen Grenzwert zu berechnen kann einerseits die [[Regel von de L'Hôpital]] oder das [[Squeezingtheorem]] verwendet werden.

## Definition
Der zweiseitige Grenzwert existiert genau dann, wenn sowohl der linksseitige als auch der rechtsseitige Grenzwert existiert und beide Grenzwert gleich sind.
$$
\lim_{ x \to a } f(x)=L \text{ genau dann wenn} \space\space \lim_{ x \to a^- } f(x)=L=\lim_{ x \to a^+ } f(x)
$$

### Eigentliche Grenzwerte
Alle Grenzwerte, welche eine Zahl ergeben, also $\lim_{ x \to a } = 2$ sind **eigentliche Grenzwerte**.

### Uneigentliche Grenzwerte
Alle Grenzwerte, welche $\pm \infty$ ergeben, also $\lim_{ x \to a }=\pm \infty$ sind **uneigentliche Grenzwerte**.



## Rechenregeln
Falls $a \in \mathbb{R} \cup\{-\infty,+\infty\}, \mu, \nu \in \mathbb{R}$ und 
$$
\lim_{ x \to a } f(x)=L_{1} \space\space\space \lim_{ x \to a } g(x)=L_{2}\space\space\space dann gilt:
$$
1. Der Grenzwert einer Summe (Differenz) ist gleich der Summe (Differenz) der Grenzwerte; Konstanten werden vor den Grenzwert gezogen
	$$
\lim_{ x \to a } [\mu f(x) \pm \nu g(x)]=\mu \lim_{ x \to a } f(x) \pm \nu \lim_{ x \to a } g(x) = \mu L_{1}\pm \nu L_{2}
$$
2. Der Grenzwert eines Produktes ist gleich dem Produkt der Grenzwerte
$$
\lim_{ x \to a } [f(x)\cdot g(x)] = \lim_{ x \to a } f(x) \cdot \lim_{ x \to a }g(x) = L_{1} \cdot L_{2} 
$$
3. Ist $L_{2}\ne 0$ und $d$in einer Umgebung von $a$ verschieden von $0$, dann ist der Grenzwert des Quotienten gleich dem Quotient der Grenzwerte.
$$
\lim_{ x \to a } \frac{f(x)}{g(x)}=\frac{\lim_{ x \to a }f(x)}{\lim_{ x \to a } g(x)}=\frac{L_{1}}{L_{2}} 
$$
4. $\lim_{ x \to a }x^n=(\lim_{ x \to a }x)^n=a^n$
5. $\lim_{ x \to a }[f(x)]^n=(\lim_{ x \to a }f(x))^n$
6. Für ein Polynom $p(x)=c_{0}+c_{1}x+\dots+c_{n}x^n=\sum_{k=0}^n c_{k}x^k$ gilt:
$$
\lim_{ x \to a } p(x) = c_{0}+c_{1}a+\dots+c_{n}a^n=p(a)
$$


## Grundlegende Grenzwerte
- $\lim_{ x \to a }k =k$
- $\lim_{ x \to a }x=a$
- $\lim_{ x \to 0^- } \frac{1}{x}=-\infty$
- $\lim_{ x \to 0^+ } \frac{1}{x}=+\infty$

