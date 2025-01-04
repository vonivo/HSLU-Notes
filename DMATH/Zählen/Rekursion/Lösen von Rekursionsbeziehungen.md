
Um eine [[Rekursionsbeziehungen]] zu lösen, werden folgende Schritte ausgeführt:
1. Bestimme die allgemeine Lösung $\left\{a_{n}^{(h)}\right\}$ der zugehörigen [[Eigenschaften von Rekursionsbeziehung|homogenen]] Rekursionsbeziehung (RHS Null setzen)
$$
a_{n}-c_{1}a_{n-2}-c_{2}a_{n-2}-c_{k}a_{n-k} =0
$$
	Um diese Gleichung zu lösen wird der Anstatz $a_{k} =r^{k}$ verwendent.
	Bei der Lösung ist nur die **nicht triviale Lösung, also $r\neq 0$ relevant**
	Ist $F$ von $k=1$ Ordnung entsteht eine [[Lineare Gleichungsysteme|lineares Gleichungssystem]] und wenn $k=2$ ein quadratisches.
	**Linear**
	Die Lösung allgemeine homogenen RB wird so ermittelt:
	$$
a_{n}^{(h)}=\alpha r^{n}
$$
	**Quadratisch**
	Die Lösung der homogenen RB wird bei **einer Doppellösung** so bestimmt:
	$$
	a_{n}^{(h)}=(\alpha_{1}+\alpha_{2})r^{n}
	$$
	Und bei zwei verschiedenen Lösungen so:
	$$
	a_{n}^{(h)}=\alpha_{1}r_{1}^{n}+\alpha_{2}r_{2}^{n}
	$$
	
2. Bestimme eine (einzige) partikuläre Lösung $\left\{a_{n}^{(p)}\right\}$ der inhomogen Rekursionsbeziehung.
 $$
a_{n}-c_{1}a_{n-2}-c_{2}a_{n-2}-c_{k}a_{n-k} =r(n)
$$
	Hier wird für $r(n)$ eine möglichst ähnliche Form verwendent:
	**Konstant**
	$k$
	**Lineare**
	$c_{1}n+c_{0}$
	**Quadratisch**
	
	**Exponential**
	$c(basis)^{n}$
1. Dann ist die allgemeine Lösung der inhomogenen Rekursionsbeziehung die Summe dieser beiden Lösungen:
$\{a_{n}\}=\left\{a_{n}^{(h)}\right\}+\left\{a_{n}^{(p)}\right\}$

- Wollen wir nun eine spezielle Lösung der inhomogenen RB, müssen die Konstanten bestimmt werden.
- Dazu wird $\{ a_{n} \}$ in die Rekursionsgleichung eingesetzt.
- Dann werden die Konstanten so gewählt, dass die Anfangsbedingungen erfüllt sind.
- Dies führt typischerweise auf ein Gleichungssystem.

## Beispiel
### Beispiel 1
Lösen sie die Rekursionsbeziehung $a_{n}=3a_{n-1}+2n$ auf (Anfangsbestimmung: $a_{1}=0$):
1. Lösung der allgemeinen linearen homogenen RB:
$$
\begin{align}
a_{n}&=3a_{n-1}+2n \\
a_{n}-3a_{n-1}&=0 \\
\text{"Anastz }r^{n}\text{ verwenden} \\
r^{n}-3r^{n-1} &= 0 \\
r^{n-1}(r-3)&=0 \\
r&=3 \\
\text{Also lautet die Lösung der allgeimen homengenen RB so:} \\
a_{n}^{(h)}&=(\alpha)3^{n}
\end{align}
$$
2. Finden **einer** Partikulären Lösung von $a_{n}=3a_{n-1}+2n$:
$$
\begin{align}
a_{n}^{(p)}&=c_{1}+c_{0} \\
a_{n}^{(p)}-3a_{n-2}^{(p)}&=2n \\
(c_{1}n+c_{0})-3(c_{1}(n-1)-c_{0})&=2n \\
c_{1}n+c_{0}-3(c_{1}n-c_{1}+c_{0})&=2n \\
c_{1}n+c_{0}-3c_{1}n+3c_{1}-3c_{0}&=2n \\
-2c_{1}n+3c_{1}-2c_{0}&=2n+0 \\
n(-2c_{1})+(3c_{1}-2c_{0})&=2n+0 \\
\text{Mittels koffizeinte vergleich entshte folgens System}
\end{align}
$$
$$
\left|
\begin{align}
-2c_{1} &=2 \\
3c_{1}-2c_{0}&=0
\end{align}
\right|
$$
Darus folgt:
$$
\begin{align}
c_{1}&=-1 \\
c_{2}&=-\frac{3}{2}
\end{align}
$$
Und somit lautete $a_{n}^{(p)}$
$a_{n}^{(p)}=-1n+\left( -\frac{3}{2} \right)$

3. Nun lösen wir  $\{a_{n}\}=\left\{a_{n}^{(h)}\right\}+\left\{a_{n}^{(p)}\right\}$
$$
\begin{align}
\{a_{n}\}&=\left\{a_{n}^{(h)}\right\}+\left\{a_{n}^{(p)}\right\} \\
&=\alpha3^{n}-1n+\left( -\frac{3}{2} \right) \\
\end{align}
$$
Nun werden die Anfangsbestimmungen eingesetzt:
$$
\begin{align}
0&=\alpha{3}^{1}-1-\frac{3}{2} \\
&=\alpha3-\frac{5}{2} \\
\frac{5}{2}&=3a \\
\frac{5}{6}&=\alpha
\end{align}
$$
=> **Spezielle Lösung**
$a_{n}^{(s)}=\frac{5}{6}3^{n}-n-\frac{3}{2}$

### Beispiel 2
Bestimme die Lösungen der RB. $a_{n}=5a_{n-1}-6a_{n-2}+7^{n}$
$a_{n}-5a_{n-1}+6a_{n-2}=7^{n}$

1. Lösung von $a_{n}^{(h)}$: Ansatz $r^{k}=a_{k}$
$$
\begin{align}
a_{n}-5a_{n-1}+6a_{n-2}&=0 \\
r^{n}-5^{n-1}+6r^{n-2}&=0 \\
r^{n-2}(r^{2}-5r+6)&=0 \\
\implies r_{1,2}&=\frac{5\pm \sqrt{ 5^{2}-4\cdot 1\cdot 6 }}{2} \\
r_{1}&= 3 \\
r_{2}&=2
\end{align}
$$
=> $a_{n}^{(h)} = \alpha_{1}2^{n}+\alpha_{2}3^{n}$
2. Partikuläre Lösung: Ansatz $a_{n}^{(p)}=c{7}^{n}$
$$
\begin{align}
a_{n}^{(p)}-5a_{n-1}^{(p)}+6a_{n-2}^{(p)}&=7^{n} \\
c7^{n}-5c7^{n-1}+6c7^{n-2}&=7^{n} \\
c7^{n-2}(7^{2}-5\cdot7+6) &=7^{n} \\
c7^{n-2}(20)&=7^{n} \\
c7^{n-2}&=\frac{7^{n}}{20} \\
c&=\frac{7^{n}}{20\cdot 7^{n-2}} \\
c&=\frac{49}{20}
\end{align}
$$
=> $a_{n}^{(p)}=\frac{49}{20}7^{n}$

3. Superposition
$$
\begin{align}
\{a_{n}\}&=\left\{a_{n}^{(h)}\right\}+\left\{a_{n}^{(p)}\right\}  \\
&=\alpha_{1}2^{n}+\alpha_{2}3^{n}+\frac{49}{20}7^{n}
\end{align}
$$
