Strebt $\Delta x$ in der [[Differentialquotient|Definition der Ableitung]] von der positiven Seite gegen null, erhält man die **rechtsseitige Ableitung** von $f$ an der Stell $x_{0}$:
$$
f'(x_{0}^+) = \lim_{ \Delta x \to 0^+ }\frac{f(x_{0}+\Delta x) - f(x_{0})}{\Delta x} 
$$
analog **linksseitige Ableitung**.

## Beispiel
Für die Betragsfunktion $y=f(x)=\lvert x \rvert$ existieren an der Stelle 0 lediglich die **rechtsseitige Ableitung** und die **linksseitige Ableitung**
![[Betrags_funktion.png]]
Rechts:
$$
\begin{align}
f'(0^+)&=\lim_{ \Delta x \to 0^+ } \frac{\lvert 0+\Delta x \rvert - \lvert 0 \rvert  }{\Delta x} \\
&=\lim_{ \Delta x \to 0^+ } \frac{\Delta x}{\Delta x} \\
&= 1 
\end{align}
$$Links:
$$
\begin{align}
f'(0^-)&=\lim_{ \Delta x \to 0^- } \frac{\lvert 0+\Delta x \rvert - \lvert 0 \rvert  }{\Delta x} \\ 
&=\lim_{ \Delta x \to 0^- } \frac{\lvert\Delta x \rvert}{\Delta x}  \\
&=\lim_{ \Delta x \to 0^- } \frac{-1\cdot\Delta x}{\Delta x} \\
&=\lim_{ \Delta x \to 0^+ } \frac{-\Delta x}{\Delta x} \\
&= -1 
\end{align}
$$
Die [[Ableitung]] $f'(0)$ ist wegen $f'(0^-)\ne f'(0^+)$ **nicht definiert!**
