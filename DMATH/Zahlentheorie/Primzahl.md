>[!Info]
>Eine positive Zahl $n\in\mathbb{Z}$ grösser als $1$ heisst Primzahl, wenn sie lediglich die Faktoren $1$ und $n$ hat. 
>Andernfalls heisst die Zahl *zusammengefasst*. In diesem Fall gilt: $\exists a(a\mid n \land(1<a<n))$.(siehe. [[Quantor#Existenzquantor|Existenzquantor]], [[Division]]).

Primzahlen lassen sich z.B. mit dem [[Sieb von Eratosthenes]] finden.

>[!Theorem]
>Es gibt unendlich viele Primzahlen.

**Beweis** [[Indirekter Beweis#Beweis durch Kontradiktion]]
1. Angenommen es gibt nur endlich viele Primzahlen $p_{1},p_{2},p_{3},\dots ,p_{3}$. Betrachtet dann die Zahl $Q=p_{1}p_{2}\dots p_{n}p_{n}+1$.
2. Nach dem [[Fundamentalsatz der Arithmetik]] ist $Q$ entweder eine Primzahl oder kann als Produkt von zwei oder mehreren Primzahlen geschrieben werden.
3. Keine Zahlen $p_{j}$ teilt aber $Q$, da immer $Q \text{ mod } p_{j}=1$ gilt. Also ist $Q$ eine Primzahl. Diese ist aber grösser als jedes $p_{j}$ in der Liste und somit nicht in der Liste enthalten.
4. Dies ist im Weiderspruch zur Annahme, dass die obige Aufzählung vollständig ist: also ist die Annahme flasch, dass es nur endlich viele Primzahlen gibt. Somit haben wir gezeigt, dass es unendlich viele Primzahlen gibt.

>[!Theorem]
>Die Anzahl Primzahlen kleiner gleich $x$ kann für sehr grosse $x$ abgeschätzt werden durch
>$$
>\pi(x) \approx \frac{x}{\ln x}
>$$

>[!Theorem]
>Es gilt:
>$$
>\lim_{ n \to \infty } \frac{\pi(n)}{\frac{n}{\ln n}}=1
>$$

=> die Anzahl der Primzahlen wächst ungefährt so schnell wie die Funktion $\frac{n}{\ln(n)}$.
Daher $\pi(n)\approx \frac{n}{\ln(n)}$

## Beispiel
**Aufgabe**: Berechne die ungefähre Anzahl aller Primzahlen 200-Stelliger Primzahlen.


- Grösse 200-stellige Zahl $x_{g}=999\dots{9} = 10^{200}-1$ (200 Stellen).
- Kleinste 200-Stellige Zahl $x_{k}=1000\dots{0} = 10^{199}$ (200 Stellen)
- Nun berechnen wir $\pi(x_{g})$
$$
\begin{align}
\pi(x_{g})&=\frac{x_{g}}{\ln x_{g}} \\
&=\frac{10^{200}-1}{\ln(200-1)}
\end{align}
$$
- Dasselbe machen wir jetzt nun mit $x_{k}$
$$
\begin{align}
\pi(x_{k})&=\frac{x_{k}}{\ln x_{k}} \\
&=\frac{10^{199}}{\ln(199)}
\end{align}
$$
- Um nun die Anzahl aller 200-Stelligen Primzahlen zu berchnen, subtrahieren wir nun die Anzahl aller Primzahlen **kleiner als die kleinste 200-Stellige Zahl** von der Anzahl aller Primzahlen welche kleiner als die **grösse 200-Stellige Zahl** sind:
$$
\begin{align}
\text{Anzahl aller 200-Stelligen Primzahlen} &= \pi(x_{g})-\pi(x_{k}) \\
&=\frac{10^{200}-1}{\ln(200-1)} -\frac{10^{199}}{\ln(199)} \\
&\approx \frac{10^{200}}{\ln(10^{200})}-\frac{10^{199}}{\ln(199)} \\
&\approx \frac{10^{200}}{200\ln(10)}-\frac{10^{199}}{199\ln(10)} \\
&\approx \frac{1}{199\cdot 200 \cdot \ln(10)}(199 \cdot 10^{200}-200\cdot 10^{199}) \\
&\approx \frac{1}{3.98\cdot10^{4}\cdot \ln(10)}(19.9-2)10^{201} \\
&\approx \frac{17.9\cdot10^{201}}{3.98\cdot 10^{4}\ln(10)} \\
&\approx 1.95\cdot 10^{197}
\end{align}
$$
Es gibt $x_{g}-x_{k}$ 200-Stellige Zahlen:
$$
10^{200}-10^{199} = (10-1)10^{199} =9*10^{199}
$$
Der Anteil an Primzhalen aller 200-Stelliger Zahlen ist nun
$$
\frac{1.95*10^{197}}{9*1^{199}}=2.16*10^{-3}\widehat{=}2.16\%
$$
