Bei **Extremwertproblemen** sucht man den Extremwert einer [[ANLIS/SW01/Funktionen/Funktion]] für ein bestimmtes Problem, z.B. maximales Volumen, minimale Distanz, etc.

## Allgemeines Vorgehen
1. Zuerst bestimmt man die Funktion, welche das Problem beschreibt.
2. Aus den Nullstellen der [[Ableitung]] $(f'(x)=0)$ erhält man Kandidaten für Stellen ($x_{0}$), an denen die Funktion [[Extrema]] annimmt.
3. Mithilfe der höheren Ableitungen an diesen Stellen überprüft man, ob es sich dabei um [[Extrema|Minima]], [[Extrema|Maxima]] oder [[Wende-und Sattelpunkte|Sattelpunkte]] handelt
4. Die Funktionswerte der gefunden relativen Maxima (Minima) werden mit den Werten der Funktion an ihren Rändern verglichen. Der grösste (kleinste) Wert ist der gesuchte Extremwert.


## Beispiel
Sie wollen das Volumen $V$ mit einem Zylinder **minimaler Oberfläche** erschließen. Wie ist das Verhältnis von Höhe zu Durchmesser.
$$
\begin{align}
V&=r^2\pi h &=V(r,h)\\
A&=2r^2\pi+h\cdot 2r\pi&=A(r,h)
\end{align}
$$
Wir wollen $A$ minimieren mit Nebenbedingung $V$.
$$
\begin{align}
V &= r^{2}\pi h \\
h=\frac{V}{r^{2}\pi}
\end{align}
$$
In $A$ einsetzen
$$
\begin{align}
A&=2r^{2}\pi+\frac{V}{r^{2}\pi}\cdot 2r\pi \\
A&=2r^{2}\pi+\frac{V}{r}\cdot 2
\end{align}
$$
$A$ nach $r$ ableiten:
$$
\begin{align}
A'&=4r\pi+\left(\frac{2V}{r}\right)' \\
A'&=4r\pi+2v\cdot(r^{-1})' \\
A'&=4r\pi+2v\cdot-1(r^{-2}) \\
A'&=4r\pi-\frac{2V}{r^2}
\end{align}
$$
Nun wird das gleich $0$ gesetzt und nach $r$ umgeformt;
$$
\begin{align}
0&=4r\pi-\frac{2v}{r^2} \\
4r\pi &= \frac{2V}{r^3} \\
4r^3\pi&=2V \\
2r^3\pi = V \\
r^3=\frac{V}{2\pi} \\
r_{0}=\sqrt[3]{\frac{V}{2\pi}  }
\end{align}
$$
Nun haben wir die Extrema für $r$. Jetzt müssen wir mit der zweiten Ableitung überprüfen, ob es wirklich ein Minima für A ist:
$$
\begin{align}
A''&=4\pi-2V\cdot (r^{-2})' \\
A''&=4\pi-2V\cdot -2(r^{-3}) \\
A''&=4\pi+\frac{4V}{r^3}
\end{align}
$$
Nun können wir das errechnete $r$ in die zweite Ableitung einsetzen:
$$
\begin{align}
A''(r_{0}) &= 4\pi+\frac{4V}{\left(\sqrt[3]{\frac{V}{2\pi}  }\right)^3} \\
A''(r_{0}) &= 4\pi+\frac{4V}{\frac{V}{2\pi}}  \\
A''(r_{0}) &= 4\pi+4V \cdot \frac{2\pi}{V} \\
A''(r_{0}) &= 4\pi+8\pi \\
A''(r_{0}) &= 12\pi
\end{align}
$$
Da es sich bei $12\pi$ um ein Minimum handelt ist somit alles korrekt. Wir wollen A minimieren.

Nun wollen wir noch das Verhältnis von der Höhe $h$ zum Durchmesser $2r$ bestimmen:
$$
\begin{align}
Q &= \frac{h}{d}
\end{align}
$$
Damit das berechnet werden kann, muss zuerst noch $h$ so umgeformt werden, dass es kein $r$ mehr enthält:
$$
\begin{align}
h&=\frac{V}{r^{2}\pi} \\
&=\frac{V}{\pi}\cdot\left( \sqrt[3]{\frac{V}{2\pi}  } \right)^{-2} \\
&= \frac{V}{\pi}\cdot \frac{(2\pi)^{2/3}}{V^{2/3}} \\
&= V\cdot V^{-2/3} \cdot2^{2/3}\cdot \pi^{-1}\cdot \pi^{2/3} \\
&= V^{1/3}\cdot 2^{2/3} \cdot \pi^{-1/3} \\
&= \sqrt[3]{ \frac{4V}{\pi} }
\end{align}
$$
Nun kann das eingesetzt werden:
$$
\begin{align}
Q &= \frac{h}{d} \\
&= \frac{\sqrt[3]{ \frac{4V}{\pi} }}{2\cdot\sqrt[3]{\frac{V}{2\pi}  }} \\
&= \frac{\sqrt[3]{ \frac{4V}{\pi} }}{\sqrt[3]{8\frac{V}{2\pi}  }}  \\
&= \sqrt[3]{ \frac{ \frac{4V}{\pi} }{8\frac{V}{2\pi}}}  \\
&= \sqrt[3]{ \frac{4V}{\pi} \cdot \frac{2\pi}{8V}}  \\
&= \sqrt[3]{ \frac{1}{\pi} \cdot \frac{2\pi}{2}}  \\
&= \sqrt[3]{ \frac{1}{1} \cdot \frac{1}{1}}  \\
&= 1
\end{align}
$$
$\implies$ Das Verhältnis liegt bei $1$.