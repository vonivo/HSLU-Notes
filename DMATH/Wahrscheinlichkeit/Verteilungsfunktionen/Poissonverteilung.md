Im Grenzfall $p\to0$ und $n\to \infty$ kann man $\mu =np$ setzen und näherungsweise die wesentlich einfachere Poissonverteilung
$$
f(k)=\frac{\mu^{k}}{k!}e^{-\mu}, (k=0,1,2,,\dots)
$$
anstelle der [[Binomialverteilung]] verwenden.

**Beispiel**
Die Wahrscheinlichkeit bei der Grippenimpfung an Nebenwirkungen zu erkranken sei $p=0.001$. Nun werden $n=2000$ Personen geimpft. Wie gross ist die [[Wahrscheinlichkeit]], dass 
(a) genau 3 Personen 
(b) mehr als 2 Personen 
an diesen Nebenwirkungen erkranken.

a)
$$
\begin{align}
\mu&=2000\cdot {0}.001 = 2 \\
f(3)&=\frac{2^{3}}{3\cdot2\cdot 1}e^{-2} \approx 0.18
\end{align}
$$
b)
Da die Aufgabenstellung "mehr als 2 Personen" lautet, muss hier die Gegenwahrscheinlichkeit berechnet werden, dass 2 oder weniger Personen erkrankten als:
$1-p(0)-p(1)-p(2)$
$$
p(>2) = 1-\frac{2^{0}}{0!}e^{-2}-\frac{2^{1}}{1!}e^{-2}-\frac{2^{2}}{2!}e^{-2} \approx 0.323
$$
