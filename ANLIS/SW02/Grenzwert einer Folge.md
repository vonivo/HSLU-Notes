[[Reelle Zahlenfolgen]] können einen Grenzwert haben. Zum Beispiel:
$$
n \mapsto a_{n} = 1-\frac{1}{n}
$$
wird mit grosser Wahrscheinlichkeit gegen 1 streben. Dies kann grafisch dargestellt werden:
![[Grenzwert_Folge.png]]

Ab welchem Glied sind alle nachfolgenden Glieder näher bei $1$ als $\epsilon = 0.01$.

## $\epsilon$-Umgebung
Die $\epsilon$-Umgebung ist der rot markierte Teppich um den Grenzwert $a$. Damit nun der Grenzwert erreicht ist, muss die Zahl $x$ welche eine Zahl aus der Folge $(a_{n})$ ist, immer innerhalb dieses Teppichs sein.
$$
U_{\epsilon}(a)=\{x \in \mathbb{R}|a-\epsilon \lt x \lt a+\epsilon\} = (a-\epsilon, a+\epsilon)^1
$$
![[Epsilon_Umgebung.png]]
### Rechenbeispiel
Wir haben die $U_{\epsilon}(\color{red}1\color{black})$, also die $\epsilon$-Umgebung von dem Grenzwert 1. Es gilt $\epsilon = 0.05$. Die Folge ist $a_{n}=1-\frac{1}{n}$.
Wir wissen, dass $|a_{n}-\color{red}1\color{black}|\lt \epsilon, \forall n >n_{0}$. $n_{0}$ ist nun das $n$ ab dem alle $a_{n}$ innerhalb des Teppichs liegen.
$$
\begin{align}
|a_{n}-\color{red}1\color{black}| &\lt \epsilon \\
|1-\frac{1}{n}-\color{red}1\color{black}| &\lt \epsilon \\
|\frac{1}{n}| &\lt \epsilon \\
\frac{1}{n} &\lt \epsilon \\
\frac{1}{\epsilon} &\lt n \\
\implies \frac{1}{0.05} &\lt n
\end{align}
$$
Strebt eine Folge im Unendlichen nach einer Zahl so **konvergiert** und wir schreiben:
$$
\lim_{ n \to \infty }\left( 1-\frac{1}{n} \right)=1 
$$


## Rechenregeln mit Grenzwerten
Falls die Folge $(a_{n})$ gegen $a$ und $(b_{n})$ gegen $b$ konvergieren:
- dann konvergiert die Folge $(a_{n} + b_{n})$ gegen $a+b$:
$$
\lim_{ n \to \infty }(a_{n}+ b_{n}) = \lim_{ n \to \infty }(a_{n}) + \lim_{ n \to \infty }(b_{n}) = a+b
$$
- dann konvergiert die Folge $(a_{n} \cdot b_{n})$ gegen $a\cdot b$:
$$
\lim_{ n \to \infty }(a_{n}\cdot b_{n}) = \lim_{ n \to \infty }(a_{n}) \cdot \lim_{ n \to \infty }(b_{n})=a\cdot b
$$
- gilt zudem $b\ne 0$ und $b_{n}\ne 0, \forall n$, dann konvergiert die Folge $\left( \frac{a_{n}}{b_{n}} \right)$ gegen $\frac{a}{b}$
$$\lim_{ n \to \infty }\left( \frac{a_{n}}{b_{n}} \right) = \frac{\lim_{ n \to \infty }(a_{n})}{\lim_{ n \to \infty }(b_{n})}= \frac{a}{b}$$
- für jede stetige [[ANLIS/SW01/Funktionen/Funktion]] $f$ gilt $\lim_{ n \to \infty }f(a_{n})=f(\lim_{ n \to \infty }a_{n})$

## Nützliche Grenzwerte
#grenzwerte
$$
 \lim_{ n \to \infty }\left( 1+\frac{\alpha}{n} \right)^n = e^{ \alpha }, \forall \alpha \in \mathbb{R} 
$$
$$
\lim_{ n \to \infty }n^ke^{-n} = 0, \forall k \in \mathbb{N} 
$$
$$
 \lim_{ n \to \infty }\sqrt[n]{n} = 1 
$$
$$
\lim_{ n \to \infty } \sqrt[n]{ a } = 1
$$
$$
\lim_{ n \to \infty }\sqrt[n]{a_{1}^n+\dots+a_{p}^n  }=\operatorname{max}\{a_{1},\dots,a_{p}\}, (a_{k}\gt_{0}, k=1,dot\dots,p) 
$$
