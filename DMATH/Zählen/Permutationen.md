>[!Definition]
>Eine Permutation von $n$ verschiedenen Elementen ist eine **geordnete Anordnung** dieser $n$ Elemente. Eine $r$-Permutation von $n$ verschiedenen Elementen ist die **geordnete Anordnung von $r$** der $n$ Elemente

**Beispiel**
Schreibe alle Permutationen und 2-Permutationen von $S=\{ 1,2,3 \}$ auf.
$$
\begin{align}
(1,2,3), (1,3,2), (3,1,2), (3,2,1),(2,1,3), (2,3,1) \\
(1,2), (1,3), (2,3), (2,1), (3,2) ,(3,1)
\end{align}
$$
## Anzahl Permutationen
>[!Theorem]
>Die Anzahl von $r$-Permutationen einer Menge von $n$ Elementen ist:
>$$
>P(n,r)=n(n-1)(n-2)\dots(n-r+1) = \frac{n!}{(n-r)!}
>$$
>Beachte: Die Anzahl $n$-Permutationen einer Menge von $n$ Elemente ist $P(n,n)=n!$

**Beispiel**
Auf wie viele Arten können die ersten drei Plätze bei einem Spiel mit 100 Teilnehmern ausgewählt werden?
$$
=100(100-1)(100-2)=100*99*98=970200
$$


## Umformung
$$
\begin{align}
n(n-1)(n-2)\dots(n-r+1)&\stackrel{?}{=} \frac{n!}{(n-r)!} \\
n(n-1)(n-2)\dots(n-r+1)&= n(n-1)(n-2)\dots(n-r+1) *1 \\
&=n(n-1)(n-2)\dots(n-r+1) \frac{n-r}{n-r} \frac{n-r-1}{n-r-1}\dots \frac{2}{2} \frac{1}{1} \\
&= \frac{n!}{(n-r)(n-r-1)\dots(2)(1)} \\
&= \frac{n!}{(n-r)!}
\end{align}
$$

# Permutationen mit Wiederholung
>[!Theorem]
>Die Anzahl $r$-Permutationen bei einer Menge mit $n$ Objekten mit Wiederholung ist $n^{r}$.

=> Eine Permutation mit Wiederholung ist eine **geordnete Anordnung** von Elementen, bei der ein Element **mehrmals** vorkommen kann.

**Beispiel**
Wie viele Zeichenketten der Länge $r$ können dem Alphabet von $n=26$ Buchstaben erzeugt werden?
$r=2$
$$
(a,a)(a,b),(a,c) \dots (a,z),(b,a),(b,b),\dots (z,z)
$$
=> $26^{2}$

# Permutationen nicht unterscheidbarer Objekte
>[!Theorem]
>Die Anzahl verschiedener Permutationen von $n$ Objekten, von denen $n_{1}$ nicht unterscheibare Objekte vom Typ 1, $n_{2}$ nicht Unterscheidbare Objekte vom Typ 2, ... und $n_{k}$ nicht unterscheibare Objekte vom Typ $k$ sind, ist gegeben durch:
>$$
\frac{n!}{n_{1}!n_{2}!\dots n_{k}!}, \text{ wobei } n = \sum_{i=i}^{k}n_{i}
>$$

**Beispiel**
Gesucht ist die Anzahl Wörter, die man aus den Zeichem im Wort $SUCCESS$ erzeugen kann.

| $i(Typ)$ | Objekt | $n_{i}$(Anzahl) |
| -------- | ------ | --------------- |
| $1$      | $S$    | $3$             |
| $2$      | $U$    | $1$             |
| $3$      | $C$    | $2$             |
| $4$      | $E$    | $1$             |
Also:
$$
\begin{align}
\frac{(3+1+2+1)!}{3!*1!*2!*1!} &= \frac{7!}{3!*2!} \\
&=\frac{7*6*5*4*3*2*1}{3*2*1*2*1} \\
&=\frac{7*6*5*4}{2*1} \\
&=7*6*5*2 \\
&=420
\end{align}
$$

