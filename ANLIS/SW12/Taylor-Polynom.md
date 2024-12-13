Task Taylor-Polynom ist ein Polynom $T_{n}(x)$, welches mit einer gegebenen [[ANLIS/SW01/Funktionen/Funktion]] $f(x)$ an der Stelle $x_{0}$ möglichst gut übereinstimmt. Dies ist das **Taylor-Polynom $n$-ten Grades** $T_{n}(x)$ von $y=f(x)$ an der Stelle $x_{0}$.

Alle [[Ableitung|Ableitungen]] von $T_{n}(x)$ stimmen mit den Ableitungen von $f(x)$ an der Stelle $x_{0}$ überein.
$$
\begin{align}
T_{n}(x_{0})&=f(x_{0}) \\
T_{n}'(x_{0}) &= f'(x_{0}) \\
T_{n}''(x_{0}) &= f''(x_{0}) \\
T_{n}''(x_{0}) &= f'''(x_{0}) \\
T_{n}^{(4)}(x_{0})&=f^{(4)}(x) \\
\dots \\
T_{n}^{(n)}(x_{0})&=f^{(n)}(x)
\end{align}
$$
## Definition
Wir nehmen an, dass die Funktion $f:[a.b]\to \mathbb{R}, x \mapsto f(x)$ genügend oft stetig differenzierbar ist. Dann ist das **Taylor-Polynom $n$-ten Grades von $f$ an der Stelle $x_{0}$** definiert durch:
$$
\begin{align}
T_{n}(x) &= \sum_{k=0}^{n} \frac{f^{(k)}(x_{0})}{k!}(x-x_{0})^{k} \\
&=f(x_{0})+f'(x_{0})(x-x_{0})+\frac{f''(x_{0})}{2!}(x-x_{0})^{2}+\frac{f'''(x_{0})}{3!}(x-x_{0})^{3}+\dots
\end{align}
$$
Ist $x_{0} = 0$, nennt man $T_{n}(x)$ auch **Maclaurin-Polynom $n$-ten Grades von $f$.**

### Beispiel
#### Beispiel 1
Funktion $f(x) =e^{ x }$
Gesucht: Taylor-Polynom 3. Grades an der Stelle $x_{0} = 0$
1. Tabelle Folgende Tabelle bilden

| k | $f^{(k)}(x)$ | $f^{(k)}(x_{0})$ | $\frac{f^{(k)}(x_{0})}{k!}$ |
| ---- | ---- | ---- | ---- |
| $0$ | $e^{ x }$ | $1$ | $\color{red}1$ |
| $1$ | $e^{ x }$ | $1$ | $\color{green}1$ |
| $2$ | $e^{ x }$ | $1$ | $\color{pink}\frac{1}{2}$ |
| $3$ | $e^{ x }$ | $1$ | $\color{blue}\frac{1}{3!}$ |
2. Polynom zusammensetzen
$$
\begin{align}
T_{3}(x) &= {\color{red}1}x^0+{\color{green}1}x^{1}+{\color{pink}\frac{1}({2}}x^{2} +{\color{blue}\frac{1}{3!}}x^{3} \\
&={\color{red}1}+{\color{green}1}x+{\color{pink}\frac{1}{2}}x^{2} +{\color{blue}\frac{1}{3!}}x^{3}
\end{align}
$$

Bestimme das **Taylor-Polynom $n$-ten Grades**:
1. Taylor-Polynom wie oben bestimmen, bis es nicht mehr weiter geht oder sich wiederholt (z.B. bei Winkelfunktionen)
2. Danach Bildungsgesetz ableiten
$$
T_{n}(x) = \frac{1}{n!}x^{n}
$$

#### Beispiel 2
**Funktion**: $f(x) =\sin x$.
**Gesucht**: Taylor-Polynom n. Grades an der Stelle $x_{0} = 0$
1. Tabelle erstellen:

| k | $f^{(k)}(x)$ | $f^{(k)}(x_{0})$ | $\frac{f^{(k)}(x_{0})}{k!}$ |
| ---- | ---- | ---- | ---- |
| $0$ | $\sin x$ | $0$ | $\color{green}0$ |
| $1$ | $\cos x$ | $1$ | $\color{red}1$ |
| $2$ | $-\sin x$ | $0$ | $\color{blue}0$ |
| $3$ | $-\cos x$ | $-1$ | $\color{pink}-\frac{1}{3!}$ |
| $4$ | $\sin x$ | $0$ | $\color{yellow}0$ |
| $5$ | $\cos x$ | $1$ | $\color{orange}\frac{1}{5!}$ |
2. Polynom bilden:
$$
\begin{align}
T_{5}(x) &= {\color{green}0}\cdot x^{0}+{\color{red}1}x^{1}+{\color{blue}0}x^{2}+{\color{pink}-\frac{1}{3!}}x^{3}+{\color{yellow}0}x^{4}+{\color{orange} \frac{1}{5!}}x^{5} \\
&=x- \frac{1}{3!}x^{3}+\frac{1}{5!}x^{5}
\end{align}
$$3. Polynom ablesen
1. Mit $(-1)^{j}$ wird die Reihe alternierend gemacht: 
$$
T_{n}(x)= \sum_{j=0}^{n} \frac{(-1)^{j}}{a!}x^{a}
$$
2. Mit $2k +1$ wird erzeugt, dass es bei $j =0 \implies 1$ gibt und bei $j=1 \implies 3$ und bei $j=2 \implies 5$
$$
T_{n}(x)= \sum_{j=0}^{n} \frac{(-1)^{j}}{(2j+1)!}x^{2j+1}
$$
