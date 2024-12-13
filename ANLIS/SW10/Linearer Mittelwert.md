Der lineare Mittelwert $\bar{y}_{linear}$ der [[ANLIS/SW01/Funktionen/Funktion]] $y=f(x)$ über dem Intervall $[a,b]$ gibt an, welchen Wert diese Funktion im Mittel hat.

Die Fläche des Rechtecks der Höhe $\bar{y}$ ist gleich der Fläche unter der Kurve ([[Bestimmtes Integral]]) $y=f(x)$
![[Linearer_Mittelwert 1.png]]$$
A = \bar{y}_{linear}(b-a) = \int _{a}^{b}f(x) \, dx 
$$
>[!info]
>Der lineare Mittelwert von $f$ über $[a,b]$ ist:
>$$\bar{y}_{linear} = \frac{1}{b-a}\int _{a}^{b}f(x) \, dx $$


## Beispiel:
Berechne den Mittelwert der Funktion $f(x)=\ln x$ im Intervall $[1,5]$.
Mittelwert:
$$
\begin{align}
\bar{y}_{linear} &= \frac{1}{5-1}\int \ln x \, dx  \\
 & =\frac{1}{4}\left[ \int 1 \cdot \ln x \, dx  \right] \\
&=\frac{1}{4}\left[ [x\ln x]_{1}^{5} - \int_{1}^{5} x \cdot \frac{1}{x}\, dx  \right] \\
&=\frac{1}{4}\left[ [x\ln x]_{1}^{5} - \int_{1}^{5} 1\, dx  \right] \\
&= \frac{1}{4}[5\cdot \ln(5)-1\cdot \ln(1) - [x]_{1}^{5}] \\
&= \frac{1}{4}[5\cdot \ln(5)-1\cdot \ln(1) - [5-1]] \\
&= \frac{1}{4}[5\cdot \ln(5)-1\cdot \ln(1) - 4] \\
&= 4.404719
\end{align}
$$
