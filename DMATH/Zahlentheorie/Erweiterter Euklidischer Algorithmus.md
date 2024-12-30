Mithilfe des erweiterten euklidischen Algorithmus kann die [[Diophantische Gleichung]] gelöst werden.

1. Wir führen den "normalen" [[Euklidischer Algorithmus|euklidischen Algorithmus]] aus.
2. Umstellen der zweitletzten Gleichung nach $1$.
3. Restlichen Gleichung in umgekehrter Reihenfolge nutzen, um störende Terme zu eliminieren.

**Beispiel**
$n_{1}=211$ und $n_{2}=13$

1. Euklidischer Algorithmus
$$
\begin{align}
211 &= 16*13 +3 \\
13&=4*3+1 \\
3&=3*1+0
\end{align}
$$
2. Umstellen der zweitletzten Zeile:
$$
\begin{align}
13&=4\cdot3+1 \\
1&=13-4\cdot 3
\end{align}
$$
3. Restlichen Gleichung in umgekehrter Reihenfolge nutzen, um störende Terme zu eliminieren.
$$
\begin{align}
1&=13-4\cdot 3 \\
&=13-4(211-16*13) \\
&=13-4*211+64\cdot13 \\
&=\color{green}-4\color{black}\cdot211+\color{red}65\color{black}\cdot13
\end{align}
$$
nun haben wir $x=-4$ und $y=65$ der Diophantischen Gleichung.
![[Pasted image 20241229142519.png]]
## Schnelles Schema
Löse die [[Diophantische Gleichung]] für die Zahlen $211$ und $13$:

| $\color{blue}211$                                               | -                                                                                     | $\color{green}1$                                                             | $\color{pink}0$                                                              |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| $\color{red}13$                                                 | $\left\lfloor  \frac{\color{blue}211}{\color{red}13}  \right\rfloor=\color{purple}16$ | $\color{brown}0$                                                             | $\color{orange}1$                                                            |
| ${\color{blue}211} \text{ mod }{\color{red}13}=\color{yellow}3$ | $\left\lfloor  \frac{\color{red}13}{\color{yellow}3}  \right\rfloor=\color{teal}4$    | ${\color{green}1}- {\color{purple}16}\cdot {\color{brown}0} = \color{lime}1$ | ${\color{pink}0}-{\color{purple}16}\cdot {\color{orange}1} =\color{cyan}-16$ |
| ${\color{red}13}\text{ mod }{\color{yellow}3} = 1$              |                                                                                       | ${\color{brown}0}-{\color{teal}4}\cdot {\color{lime}1} = -4$<br>=> $x=-4$    | ${\color{orange}1}-{\color{teal}4}\cdot{\color{cyan}-16} =65$<br>$y=65$      |
=> $-4 \cdot 211 + 65 \cdot{1}3 = 1$

Jetzt lässt sich auch gut die [[Modulare Inverse]] berechnen:
$$
\begin{align}
-4 \cdot 211 + 65 \cdot{1}3 &= 1 \\
-4\cdot 211 &\equiv 1 \text{ (mod 13)} \\
\implies 9 \cdot 211 &\equiv1 \text{ (mod 13)} \\
\implies 9 \cdot 3 &\equiv1 \text{ (mod 13)}
\end{align}
$$
