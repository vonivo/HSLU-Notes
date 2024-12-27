>[!Definition]
>Die Binomialverteilung liefert die [[Wahrscheinlichkeit]] für exakt $k$ Erfolge bei $n$ **unabhängigen** [[Bernoulliverteilung|Bernoulliexperimenten]] mit Erfolgswahrscheinlichkeit $p$:
>$$
>B(k|n,p) = B_{n,p}(k)=C(c,k)p^{k}(1-p)^{n-k}=\begin{pmatrix}
n \\
k
\end{pmatrix}p^{k}(1-p)^{n-k}
>$$

Die Binomialverteilung liegt vor, wenn bei einer **Stickprobe die einzelnen Objekte nach der Prüfung wieder zurückgelegt werden.** Es handelt sich um **Ziehen mit Zurücklegen.**


**Beispiel 1**
Wir erzeugen $n=3$ Bits, wobei de Wahrscheinlichkeit, für eine Eins (Erfolg) $p$ und für eine Null (Misserfolg) $1-p$ ist. Wie gross ist die Wahrscheinlichkeit fü $k=0$, $k=1$, $k=2$ und $k=3$ Einsen?

$$
\begin{align}
k&=0 &\begin{pmatrix}
3 \\
0
\end{pmatrix}p^{0}q^{3-0}=\begin{pmatrix}
3 \\
0
\end{pmatrix}q^{3} \\
k&=1 &\begin{pmatrix}
3 \\
1
\end{pmatrix}p^{1}q^{3-1}=\begin{pmatrix}
3 \\
1
\end{pmatrix}p^{1}q^{2} \\
k&=2 &\begin{pmatrix}
3 \\
2
\end{pmatrix}p^{2}q^{3-2}=\begin{pmatrix}
3 \\
2
\end{pmatrix}p^{2}q^{1} \\
k&=3 &\begin{pmatrix}
3 \\
3
\end{pmatrix}p^{3}=\begin{pmatrix}
3 \\
3
\end{pmatrix}p^{3}
\end{align}
$$
Oder als [[Bäume|Baum]]
![[Pasted image 20241227093806.png]]

**Beispiel 2**
Eine Folge von $10$ Bit wird Bit für Bit zufällig erzeugt. Dabei gilt in jedem einzelnen Erzeugungsschritt $p(0)=0.9$ und $p(1) = 1-0.9=0.1$. Mit welcher Wahrscheinlichkeit enthält die Bitfolge genau 8 Nullen?

$$
\begin{align}
B_{10,0.9}(8)&=\begin{pmatrix}
10 \\
8
\end{pmatrix}0.9^{8}\cdot0.1^{2} \\
&=\begin{pmatrix}
10 \\
2
\end{pmatrix}0.9^{8}\cdot0.1^{2} \\
&=\frac{10\cdot{9}}{1\cdot 2}(0.9)^{8}(0.1)^{2} \\
&= 45\cdot(0.9)^{8}\cdot 0.01 \\
&\approx 0.1937
\end{align}
$$
