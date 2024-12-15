>[!Info]
>Seien $f$ und $g$ [[DMATH/Funktionen/Funktion|Funktionen]] von $\mathbb{Z}$ oder ($\mathbb{R}$). Dann sagt man $f(x)$ ist $\mathcal{O}(g(x))$ falls es Konstanten $C$ und $k$ gibt, sodass gilt:
>$|f(x)\le C|g(x)|, \forall x>k$ Gelesen: $f(x)$ is gross-O von $(g(x))$; man schreibt $f(x) \in\mathcal{O}(g(x))$.

- Für $g(x)$ wird eine möglichst **einfache**, **nicht zu schnell wachsende** Funktion wie z.B. $x,x^{2},\dots,x^{n},2^{x},\ln x, x\ln x$, etc. gewählt.
- Das Ziel von der [[Big-O-Notation]] ist herauszufinden, wie sich $f(x)$ für sehr grosse $x$ verhält.
- $k$ ist der kleinste Wert von $x$ für den die obige Ungleichung noch gilt.
- Die Konstanten $K$ und $C$ nennt man auch **Zeugen** der [[Big-O-Notation]].

>[!Warning]
>Für das Polynom $f(x)=\sum_{k=0}^{n}a_{k}x^{k}=a_{0}+a_{1}x+a_{2}x^{2}\dots\mp a_{n}x^{n}$ mit *reellen Koeffizienten* $a_{k}(k=0,1,2,3\dots,n)$ gilt $f(x)$ ist $\mathcal{O}(x^{n})$ -> **die höchste Potenz von $x$ ist bestimmend**.

**Beweis**
$$
f(x) =| \sum_{k=0}^{n}a_{k}x^{k}| \leq\sum_{k=0}^{n}\frac{|a_{k}|}{x^{n-k}}\le x^{n}\sum_{k=0}^{n}|a_{k}|
$$
Mit den Zeugen $C=\sum_{k=0}^{n}|a_{k}|$ und $k=1$.
**Beispiel:** $x^{5}-3x^{3}+2x^{2}-13$ ist $\mathcal{O}(x^{5})$ mit den Zeugen $k=1$ und $C=|1|+|-3|+|2|+|-13|=19$.

## Beispiel
### Anleitung
**Zeige:** $f(x)=x^{2}+2x+1$ ist $\mathcal{O}(x^{2})$.
**Lösung:**
- Wir betrachten **nur reelle Zahlen** $x$ mit $x>1$.
- Wir suchen den Teil des Polymnoms welcher am schnellsten wächst (siehe [[Big-O-Notation]]) -> In unserem fall $x^{2}$.
- Nun wird wie folgt vorgegangen:
	- Wir ersetzen alle weiteren Teile des Polynoms, mit $x^{2}$.
	- Wir Notieren, für welches $x$ gilt $x^{2}>\text{ zu ersetzenden Teil}$. Das höchste $x$ wird unser $k$.
	- In unserem Fall ist $k=1$ da $1^{2}\ge 1$ 
$$
|f(x)|=|x^{2}+2x+1|=x^{2}+2x^{2}+x^{2}
$$
- Nun wird das ganze vereinfacht:
$$
\begin{align}
|f(x)|=|x^{2}+2x+1|&\le x^{2}+2x^{2}+x^{2} \\
&\le 4x^{2}
\end{align}
$$
- Die Konstante vor $x^{2}$ ist nun unser $C$.
=> also $f(x)=x^{2}+2x+1$ is $\mathcal{O}(x^{2})$ mit den Zeugen $k=1$ und $C=4$.

### Beispiel 2
**Zeige**:$f(x) = n\log(n^{2}+1)+n^{2}\log(n)$
$$
\begin{align}
f(x)&=n\log(n^{2}+1)+n^{2}\log(n)\\
&\le n\log(2n^{2})+n^{2}\log(n), n\geq 1 \\
&\le n\log(n^{2})+n\log(2)+n^{2}\log(n), n\geq 1  \\
&\le 2n\log(n)+n\log(2)+n^{2}\log(n), n\geq 1  \\
&\le n^{2}\log(n)+n^{2}\log(n)+n^{2}\log(n), n\geq 2 \\
&\le 3n^{2}\log(n)
\end{align}
$$
$f(x)$ ist $\mathcal{O}(n^{2}\log n)$ für $k=2$ und $C=3$


## Abschätzung der Fakultät
Find die Abschätzung für die Fakultät:
$$
n\neq\begin{cases}
1,&\text{falls } n=0 \\
n(n-1)\dots2\cdot1, &\text{falls }n>0
\end{cases}
$$
sowie für $\log(n!)$.
$$
\begin{align}
\ln(n!)&=\ln(n(n-1)(n-2)\dots2\cdot 1) \\
&=\ln(n)+\ln(n-1)+\ln(n-2)\dots \ln(2)+\ln(1) \\
&\leq\ln(n)+\ln(n)+\ln(n)\dots \ln(n)+\ln(n) &,n > 1 \\
&\leq n\ln(n) \\
&\leq \ln(n^{n})
\end{align}
$$
für $C=1$ und $k=1$.
=> $\ln(n!)\leq \ln(n^{n})$ => $n!\leq n^{n}$
