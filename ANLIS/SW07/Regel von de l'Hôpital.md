>[!info]
>Wir nehmen an, dass $f$ und $g$ in einer Umgebung von $x=a$ *differenzierbar* sind und $\lim_{ x \to a }f(x)$ und $\lim_{ x \to a }g(x) = 0$ sind. Dann gilt $\lim_{ x \to a } \frac{f(x)}{g(x)} = \lim_{ x \to a } \frac{f'(x)}{g'(x)}$ falls die rechte Seite existiert oder $\pm \infty$ ist.
>Weiter gilt die Regel auch für Grenzübergange $x\to a^{-}, x\to a^+, x\to \infty$ und $x\to-\infty$

**Kurz:** der [[Grenzwert]] von einem Ausdruck, welcher $\lim_{ x \to a }\frac{f(x)}{g(x)} = \frac{0}{0}$ oder $\frac{\infty}{\infty}$ entspricht, gilt: $\lim_{ x \to a }\frac{f(x)}{g(x)} = \lim_{ x \to a }\frac{f'(x)}{g'(x)}$

Man kann also den [[Grenzwert]] über die [[Ableitung]] errechnen.

>[!warning]
>Diese Regel kann und muss teilweise mehrmals hintereinander angewendet werden.


## Beispiel
Gesucht: $\lim_{ x \to 0 } \frac{\sin(x)}{x}$

Lösung
$$
\begin{align}
\lim_{ x \to 0 } \frac{\sin x}{x} &=\lim_{ x \to 0 }\frac{(\sin x)'}{x'} \\
&=\lim_{ x \to 0 }\frac{\cos(x)}{1} \\ 
&=\frac{\lim_{ x \to 0 }\cos(x)}{1} \\
&=\frac{\cos(0)}{1} \\
&=\frac{1}{1} \\
&=1
\end{align}
$$



