Die hypergeometrische Verteilung behandelt (im Gegensatz zur [[Binomialverteilung]]) das Ziehen mit Zurücklegen und ist aus der [[Binomialverteilung]] hervorgegangen.

Angenommen wir haben eine Schachtel mit Schrauben, wobei eine Teilmenge davon Defekte ist.

>[!Definition]
>$$
>p(k)=\frac{\begin{pmatrix}
M \\
k
\end{pmatrix}\begin{pmatrix}
N-M \\
n-k
\end{pmatrix}}{\begin{pmatrix}
N \\
n
\end{pmatrix}}
>$$

1. $n$ Teile können aus $N$ Teilen auf $\begin{pmatrix}N\\n\end{pmatrix}$ Arten ausgewählt werden => Alle möglichen Fälle.
2. $k$ defekte Teile können aus $M$ defekten Teilen auf $\begin{pmatrix}M\\k\end{pmatrix}$ Arten ausgewählt werden.
3. $(n-k)$ nicht defekte Teile können aus $(N-M)$ nicht defekten Teilen auf $\begin{pmatrix}N-M\\n-k\end{pmatrix}$ Arten ausgewählt werden.

**Beispiel**
In einer Schachtel befinden sich 10 Ventile von denen 3 defekt sind. Nun entnimmt man der Schachtel zwei Ventile **ohne Zurücklegen**. Wie gross ist die Wahrscheinlichkeit, dass $0,1$ oder $2$ Teile defekt sind?
$$
\begin{align}
p(0)&=\frac{\begin{pmatrix}
3 \\
0
\end{pmatrix}\begin{pmatrix}
10-3 \\
2-0
\end{pmatrix}}{\begin{pmatrix}
10 \\
2
\end{pmatrix}}&=\frac{21}{45} &\approx 0.4\bar{6} \\
p(1)&=\frac{\begin{pmatrix}
3 \\
1
\end{pmatrix}\begin{pmatrix}
10-3 \\
2-1
\end{pmatrix}}{\begin{pmatrix}
10 \\
2
\end{pmatrix}}&=\frac{21}{45} &\approx 0.4\bar{6} \\
p(2)&=\frac{\begin{pmatrix}
3 \\
2
\end{pmatrix}\begin{pmatrix}
10-3 \\
2-2
\end{pmatrix}}{\begin{pmatrix}
10 \\
2
\end{pmatrix}}&=\frac{3}{45} &\approx 0.0\bar{6}
\end{align}
$$
