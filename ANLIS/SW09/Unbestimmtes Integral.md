Das [[Bestimmtes Integral|Bestimmte Integral]] $\int _{a}^{b}f(t) \, dt$ repräsentiert den Flächeninhalt $A$
zwischen der Kurve $y=f(t)$ un der $t$-Achse im Intervall $a\leq t\leq b$.
![[Unbestimmtest_Integral_1.png]]
Wenn nun die obere Grenze $b$ variabel wird, hängt der Wert von der Fläche $I$ davon ab:
$$
I(x) = \int _{a}^{x} f(t)\, dt 
$$
![[Unbestimmtest_Integral_2.png]]
Mann nennt diese Funktion **unbestimmtes Integral** oder **[[Funktion|Flächenfunktion]]** von $f(t)$, da die obere Grenze variabel ist.

Wählt man nun die untere Grenze $a^{*} \gt a$ so ist auch 
$$
I^{*}= \int _{a^{*}}^{x}f(t) \, dt 
$$
ein unbestimmtes Integral.

Zwischen $I(x)$ und $I^{*}(x)$ existiert folgender Zusammenhang:
$$
\begin{align}
I(x)-I^{*}(x) &=\int _{a}^{x}f(t) \, dt - \int _{a^{*}}^{x}f(t) \, dt \\
&= \int _{a}^{x}f(t) \, dt+\int _{x}^{a^{*}}f(t) \, dt \\
&=\text{konstant}    
\end{align}
$$

## Eigenschaften
1. Das unbestimmte Integral $I(x) = \int _{a}^{x}f(t) \, dt$ stellt den Flächeninhalt zwischen $y(t)=f(t)$ über dem Intervall $[a;x]$ in Abhängigkeit von der oberen Grenze $x$ dar.
2. Zu jeder [[Stetigkeit|stetigen Funktion]] $f(t)$ gibt es unendliche viele unbestimmte Integrale, die sich nur durch ihre untere Grenze unterschieden.
3. Die Differenz zweier unbestimmter Integrale $I_{1}(x)$ und $I_{2}(x)$ ist eine Konstante.