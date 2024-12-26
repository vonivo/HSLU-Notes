>[!Definition]
>Eine $r$-Kombination von $n$ Elementen ist eine **ungeordnete** Auswahl von $r$ dieser $n$ Elemente. Sie ist also nichts anderes als eine Teilmenge mit $r$ Elementen.

**Beispiel**
Für $S=\{ 1,2,3,4 \}$ ist $\{ 1,3,4 \}$ eine $3$-Kombination von $S$. Dabei ist $\{ 4,1,3 \}$ **dieselbe $3$-Kombination**.

Wie viele $3$-Kombinationen von $S$ gibt es?
Mann kann argumentieren, dass anstatt 3 Elemente **ausgewählt werden** einfach **eines** Wegelassen wird. Wir können 4 Elemente weglassen, also gibt es $4$ $3-$Kombinationen.

>[!Theorem]
>Die Anzahl von $r$-Kombinationen einer Menge von $n\geq 0$ Elemente ist gegeben durch:
>$$
>C(n,r)= \frac{n!}{r!(n-r)!}=\begin{pmatrix}
n \\
r
\end{pmatrix} = C(n, n-r)
>$$
>Wobie $0\leq r\leq n$ gelten muss

Mann nennt $\begin{pmatrix}n\\r\end{pmatrix}= \frac{n!}{r!(n-r)!}$ den [[Binomialkoeffizient]].

**Beispiel**
Wie viele Teams von $3$ Personen lassen sich aus einer Gruppe von $5$ Personen bilden?
$$
\begin{align}
C(5,3)&=\frac{5!}{3!(5-3)!} \\
&=\frac{5*4*3*2*1}{3*2*1*2*1} \\
&=\frac{5*4}{2*1} \\
&=10
\end{align}
$$


## Beweisidee
Die Anzahl aller $r$-[[Permutationen]] von $n$ ist die Anzahl $r$-Kombinationen multipliziert mit der Anzahl $r$-Permutationen von $r$.
$$
\begin{align}
P(n,r)&=C(n,r)*P(r,r) \\
\frac{P(n,r)}{P(r,r)}&= C(n,r) \\
\frac{\frac{n!}{(n-r)!}}{r!} &=C(n,r) \\
\frac{n!}{r!(n-r)?}&=C(n,r)
\end{align}
$$
# Kombination mit Wiederholung
>[!Theorem]
>Die Anzahl $r$-Kombinationen bei einer Menge von $n$-Objekten mit Wiederholung ist $C(n+r-1,r)=\begin{pmatrix}n+r-1\\ r\end{pmatrix}$

Eine Kombination mit Wiederholung ist eine **ungeordnete Ansammlung** an Elementen, bei der die **Elemente** jeweils **mehrmals** vorkommen können.

**Beispiel**
Auf wie viele Arten lassen sich aus einer Früchteschale mit Äpfeln (A), Orangen (O) und Birnen (B) vier Fürchte herausnehmen, wenn es auf die Reihenfolge nicht ankommt.

*Lösung durch Kombination mit Wiederholung*
$$
\begin{align}
C(3+4-1,4)&=\begin{pmatrix}
6 \\
4
\end{pmatrix} \\
&=\frac{6*5*4*3}{4*3*2*1} \\
&=\frac{6*5}{2*1} \\
&=15
\end{align}
$$
*Lösung mittels einen Bitstring*
Wird gehen wie Folgt vor, wir denken uns drei Fächer "  1   |  2  |  3  |".
Das erste Fach repräsentiert die Äpfel, das zweite die Orangen und das dritte die Birnen.

Für jede Frucht, die wir ziehen, machen wir eine $0$ in das entsprechende Fach.
Z.B. für "AAOB" -> "$00$|$0$|$0$"

Mit etwas Fantasie können wir nun die Abtrennungen "|" als $1$ sehen.
Also haben wir jetzt einen Bitstring der Länge $6=(4+2*1)$. Wenn wir jetzt immer zwei Stellen aus diesem String auswählen und dort die $1$en setzen, haben wir immer eine gültige Ziehung.

=> Sprich die Anzahl der Möglichkeiten der Ziehung ist gleich der Anzahl Möglichkeiten $2$ Stellen aus $6$ auszuwählen. (**Kombination**).

=> $\begin{pmatrix}6\\4\end{pmatrix}=\begin{pmatrix}6\\2\end{pmatrix}=15$
