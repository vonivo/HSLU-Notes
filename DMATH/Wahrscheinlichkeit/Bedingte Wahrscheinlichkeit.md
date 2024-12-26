>[!Definition]
>Sind $A$ und $B$ zwei Ereignisse $p(B)>0$, dann bezeichnet man die [[Wahrscheinlichkeit]] von $A$ unter der Voraussetzung $B$ mit $p(A|B)$.

>[!Theorem]
>Die Wahrscheinlichkeit für das Ereignis $A$ unter der Voraussetzung, dass Ereignis $B$ eingetreten ist, ist gegeben durch:
>$$
>p(A|B) = \frac{p(A\cap B)}{p(B)}
>$$



## Beispiele
**Beispiel 1**
Beim "dreimaligen Wurf" einer **fairen Münze** wissen wir, dass beim ersten Mal Zahl geworfen wurde.
Wie gross ist die Wahrscheinlichkeit, dass eine ungerade anzahl Zahlen geworfen wurden?

$A =\{ \text{"Anzahl Zahl ist ungerade"}\} = \{ZZZ,ZKK,KZK,KKZ  \}$
$B =\{ \text{"Erseter Wurf ist Zahl"} \} = \{ ZZZ,ZZK,ZKZ,ZKK \}$

Da alle Flächen gleich wahrscheinlich sind, gilt die [[Laplaceverteilung]] und wir erhalten unter Berücksichtigung der [[DMATH/Zählen/Produktregel|Produktregel]] insgesamt $2^{3}$ Möglichkeiten für die Resultate des Münzwurfs. 

Daraus folgt die Wahrscheinlichkeit für $p(B) = \frac{4}{8}$
Die Wahrscheinlichkeit für $p(A\cap B) = \frac{2}{8}$.

Daraus folgt:
$$
\begin{align}
p(A|B) &= \frac{p(A\cap B)}{p(B)} \\
&=\frac{\frac{2}{8}}{\frac{4}{8}} \\
&=\frac{2*8}{8*4} \\
&=\frac{1}{2}
\end{align}
$$

**Beispiel 2**
Bei einem bestimmten Lottospiel muss man $6$ Zahlen zwischen $1$ und $30$ raten. Nun werden in der Ziehung die Zahlen $1,14,15,20,23$ und $27$ gezogen. Sie erfahren aber lediglich, dass die Zahl $15$ gezogen wurde. Um wie viel wird ihre Gweinnchance durch diese Information vergrössert?

Die Wahrscheinlichkeit 6 Richtige zu ziehen liegt nach [[Laplaceverteilung]] bei 
$$
\begin{align}
\frac{1}{\begin{pmatrix}
30 \\
6
\end{pmatrix}}=\frac{1}{593775}
\end{align}
$$
Wir definieren nun folgende Ereignisse:
$$
\begin{align}
A&=\text{"Die Zahlen 1,14,15,20,23,26 wurden gezogen"} \\
B&=\text{"Die Zahl 15 wurde gezogen"}
\end{align}
$$
Wir berechnen nun $p(B)$:
1. Die Anzahl der günstigen Ereignisse ist gegeben durch eine $6$-[[Kombinationen|Kombination]] der Menge $\Omega=\{ 1,2,3,\dots,30 \}$ wenn eine Zahl dieser Kombination die Zahl $15$ ist.
	Wir gehen also davon aus, das $15$ gezogen wird und noch eine Beliebige $5$-Kombination der verbleibenden $29$ Zahlen.
	=> $\begin{pmatrix}29\\5\end{pmatrix}$
2. Die Menge aller möglichen Fälle ist gegeben durch die Anzahl 6 Elemente aus 30 auszwählen.
	=>$\begin{pmatrix}30\\6\end{pmatrix}$
$$
p(B)=\frac{\begin{pmatrix}
29 \\
5
\end{pmatrix}}{\begin{pmatrix}
30 \\
6
\end{pmatrix}}=\frac{118755}{593775}
$$
Wir Berechnen nun $p(A|B)$:
1. Dafür benötigen wir die Wahrscheinlichkeit von $p(A\cap B)$. Diese Wahrscheinlichkeit. Da $A$ der Sechser ist, gibt es **genau einen Günstigen fall**
Darus folgt:
$$
\begin{align}
p(A|B) &= \frac{p(A\cap B)}{p(B)} \\
&=\frac{\frac{1}{\begin{pmatrix}
30 \\
6
\end{pmatrix}}}{\frac{\begin{pmatrix}
29 \\
5
\end{pmatrix}}{\begin{pmatrix}
30 \\
6
\end{pmatrix}}} \\ 
&=\frac{1}{\begin{pmatrix}
29 \\
5
\end{pmatrix}} \\
&=5\frac{1}{\begin{pmatrix}
30 \\
6
\end{pmatrix}}
\end{align}
$$
=> Also die Chance ist um das 5-Fache gestiegen.