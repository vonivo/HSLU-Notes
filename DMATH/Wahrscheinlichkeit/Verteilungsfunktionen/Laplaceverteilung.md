>[!Definition]
>Besteht der [[Zufallsexperiment|Stichprobenraum]] $\Omega$ aus den $n$ [[Zufallsexperiment|Elementarereignissen]] $x_{1},x_{2},x\dots,x_{n}$ die alle mit **derselben [[Wahrscheinlichkeit]] eintreten**, dann hat man die **Gleichverteilung:**
>$$
>p(x_{i})=\frac{1}{|\Omega|} = \frac{1}{n}, i=1,2,\dots n
>$$

Die [[Wahrscheinlichkeit]] eines [[Zufallsexperiment|Ereignisses]] $A$ edes endlichen [[Zufallsexperiment|Stichprobenraumes]] $\Omega$ von lauter gleich wahrscheinlichen Ergeignissen ist gegeben durch:
$$
p(A) = \frac{|A|}{|\Omega|} = \frac{\text{Anzahl günstige Fälle}}{\text{Anzahl möglicher Fälle}}
$$
## Wichtige Regeln
### Komplementärregeln
Falls $A$ ein Ereignis des Stichprobenraums $\Omega$ ist, dann gilt für das komplementäre Ereignis $\bar{A}$: $p(\bar{A}) = 1 -p(A)$

### Additionsregel
Falls $A_{1}$ und $A_{2}$ zwei Ereignisse des Stichprobenraums $\Omega$ sind, dann gilt die Additionsregel: $p(A_{1}\cup A_{2}=p(A)+p(B)-p(A\cap B))$ (siehe [[Einschluss- Ausschlussprinzip]]).


## Beispiele
**Beispiel 1**
$\Omega=\{ 1,2,3,4,5,6 \}$ (Anzahl Augen eines **fairen Würfels**). Die Wahrscheinlichkeit eine $1$ zu würfeln ist:
$$
p(1) = \frac{1}{|\Omega|} = \frac{1}{6}=p(2)=p(3)=p(4)=p(5)=p(6)
$$
**Beispiel 2**
Berechne die Wahrscheinlichkeit bei einem fairen Würfel eine Gerade Zahl zu Würfeln:
$$
\begin{align}
\Omega&=\{ 1,2,3,4,5,6 \} \\
A&=\{ 2,4,6 \} \\
p(A)&=\frac{|A|}{|\Omega|} = \frac{3}{6}=\frac{1}{2}
\end{align}
$$

**Beispiel 3**
Aus einem Top mit $4$ blauen und $5$ roten Kuglen wird eine Kugel gezogen, wie gross ist die Wahrscheinlichkeit, dass die Kugel blau ist?
$$
p(\text{"Blau"})=\frac{4}{9}
$$
**Beispiel 4**
Es werden $3$ Briefe mit entsprechenden Umschlägen an $3$ verschiedene Personen geschrieben. Leider werden die Briefe per Zufall in die jeweiligen Umschläge gesteckt. Wie gross ist die Wahrscheinlichkeit, dass **wenigstens** einer der Briefe in den richtigen Umschlag ist.

$A_{k}=\text{"Der k. Brief ist im Richtigen Umschlage}$
$$
\begin{align}
p(A_{1}\cup A_{2}\cup A_{3}) &= p(A_{1})+p(A_{2})+p(A_{3})-p(A_{1} \cap A_{2})-p(A_{1}\cap A_{3})-p(A_{2}\cap A_{3})+p(A_{1}\cap A_{2}\cap A_{3}) \\
&=\frac{1}{3}+\frac{1}{3}+\frac{1}{3}-\frac{1}{3*2}-\frac{1}{3*2}-\frac{1}{3*2}+\frac{1}{3*2*1} \\
&=1-\frac{1}{2} +\frac{1}{6} \\
&=\frac{2}{3}
\end{align}
$$
