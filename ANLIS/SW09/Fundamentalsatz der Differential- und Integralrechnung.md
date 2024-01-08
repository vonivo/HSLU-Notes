Einerseits hat man $\Delta I=I(x+\Delta x)-I(x)$ ([[Unbestimmtes Integral]]) und die Approximation $\Delta I \approx f(x)\Delta x$. Also zusammengefasst
$$
f(x) \approx \frac{I(x+\Delta x)-I(x)}{\Delta x}
$$
![[Fundamentalsatz.png]]
Man kann zeigen, dass für stetige $f$ gilt:
$$
f(x)= \lim_{ \Delta x \to 0 } \frac{I(x+\Delta x)-I(x)}{\Delta x}=I'(x)
$$
Wegen $I'(x) = f(x)$ ist also das unbestimmte Integral (oder Flächenfunktion) $I(x)$ eine [[Integration|Stammfunktion]] von $f(x)$.

>[!info]
>**Jedes unbestimmte Integral** $I(x) = \int _{a}^{x}f(t) \, dt$ der [[Stetigkeit|stetigen Funktion]] $f(x)$ is tine **Stammfunktion** von $f(x)$:
>$$
>I(x) = \int _{a}^{x}f(t) \, dt \space\space\space\space \implies I'(x)= \frac{d}{dx}\int_{a}^{x}f(t) \, dt.$$

Daraus folgt:
	1. $I(x)$ ist wegen $I'(x)=f(x)$ ein stetig [[Ableitung|differenzierbare]] Funktion.
	2. Jedes unbestimmte Integral hat die Form:
	$$
I(x)=\int _{a}^{x}f(t) \, dt = F(x)+C_{1} 
$$
3. Die **Menge aller unbestimmter Integrale** von $f(x)$ hat die Form
$$
\int f(x) \, d =F(x)+C 
$$
4. Für stetige Funktionen sind Stammfunktionen und unbestimmtes Integral dasselbe.
## Beispiel
$$
I(x) = \int (2x+1) \, dx 
$$

$$
\begin{align}
I(x) &= \int (2x+1) \, dx  \\
 & =\int 2x \, dx + \int 1 \, dx \\
&= 2\int x \, dx + x \\
 & = 2 \cdot \frac{1}{2}x^{2}+x \\
 & = x^{x}+x \\
 & = x^{x+1} + C
\end{align}
$$


