>[!info]
>Gilt für drei Funktionen $f$,$g$ und $h$ in einer Umgebung $c$ (evtl. mit Ausnahme von $c$)
>$$
>g(x)\le f(x)\le h(x) \space\space\space\space \text{und} \space\space\space\space \lim_{ a \to c } g(x) =\lim_{ x \to c } h(x) ) =L
>$$
>dann gilt auch $\lim_{ x \to c }=L$

![[Squeezing_theorem.png]]

Um den Grenzwert einer [[ANLIS/SW01/Funktionen/Funktion]] $f(x)$ an der Stelle $c$ zu bestimmen, werden zwei Funktionen gesucht, welche die Funktion $f(x)$ einschließen (hier $g(x)$ und $h(x)$) und an der Stelle $c$ denselben Grenzwert haben.

## Beispiel
Wir bestimmen den Grenzwert von der Funktion $f(x)=\frac{\sin x}{x}$ Ergibt dann $\lim_{ x \to 0 } \frac{\sin x}{x}$.
![[Squeezing_theorem_2.png]]
Jetzt werden zwei Funktionen bestimmt, welche $(f(x))$ einschliessen und an der Stelle $0$ denselben Grenzwert haben.

Die Funktion $g(x) = 1$ und $h(x)=\cos x$ umschliessen die Funktion:
![[Squeezing_3.png]]
Nun kann der Grenzwert bestimmt werden:
$$
\lim_{ x \to 0 }1 = \lim_{ x \to 0 } \cos x = 1 
$$
$\implies$ Der Grenzwert von $\lim_{ x \to 0 }\frac{\sin x}{x}$ ist $0$.