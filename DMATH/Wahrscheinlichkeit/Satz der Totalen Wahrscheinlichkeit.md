Wir betrachten zuerst zwei komplementierenden [[Menge|Mengen]]:

Gegeben:
- $B, \bar{B} \subset \Omega$ (vollständige Zerlegung) $$
\begin{align}
B\cap \bar{B}&=\emptyset \\
B\cup \bar{B}&=\Omega
\end{align}
$$
- $p(B),p(\bar{B})>0$
- Ein Ereignis $A$

Dann gilt für die [[Wahrscheinlichkeit]] des [[Zufallsexperiment|Ereignisses]] $A$ 
$$
p(A) = p(A|B)\cdot p(B)+p(A|\bar{B})\cdot p(\bar{B})
$$
![[Pasted image 20241226174137.png]]
## Beweis
$$
\begin{align}
p(A) &= p(A\cap B) + p(A\cap \bar{B}) \\
&=p(A|B)p(B)+p(A|\bar{B})*p(\bar{B})
\end{align}
$$
=> [[Bedingte Wahrscheinlichkeit]]:
$$
\begin{align}
p(A|B)&=\frac{p(A\cap B)}{p(B)} \\
p(A\cap B)&=p(A|B)p(B)
\end{align}
$$
Oder mittels eines [[Bäume|Baumes]]:
![[Pasted image 20241226174558.png]]

## Allgemeiner Fall
Vorraussetzug:
- $B_{1},\dots,B_{k}\subset \Omega$ eine vollständige Zerlelgung von $\Omega$ (paarweise disjunkte Ereignisse deren Vereinigung ganz $\Omega$ ist).
- $\forall i|p(B_{i}>0)$

>[!Theorem]
>Dann gilt für Ereignis $A$
>$$
>p(A)=\sum_{i=1}^{k}p(A\cap B_{i}) = \sum_{i=1}^{k}p(A|B_{i})p(B_{i})
>$$
>Für bedingte Wahrscheinlichkeit von $A$ unter der Voraussetzung $C$ gilt:
>$$
>p(A|C)=\frac{1}{p(C)}\sum_{i=0}^{k}p(A\cap(B_{i}\cap C))=\sum_{i=1}^{k}p(A|B_{i}\cap C)\cdot p(B_{i}|C)
>$$

![[Pasted image 20241226175815.png]]
![[Pasted image 20241226175831.png]]

### Beweis
Wir nutzen hier die Eigenschaften einer vollständigen Zerlegung vom $\Omega$ und die Definition der [[Bedingte Wahrscheinlichkeit]].
$$
\begin{align}
p(A)&=p((A\cap B_{1})\cup (A\cap B_{2})\cup\dots \cup(A\cap B_{k})) \\
&=p(A\cap B_{1})+p(A\cap B_{2})+\dots+p(A\cap B_{k}) \\
&=\sum_{i=0}^{k}p(A\cap B_{i}) = \sum_{i=0}^{k}p(A|B_{i})p(B_{i})
\end{align}
$$

## Beispiel
Aus einer Urne mit 10 weissen und 5 schwarzen Kugeln wird zweimal hintereinander je eine Kugel entzogen, wobei nicht zurückgelegt wird. Mit welcher Wahrscheinlichkeit ist die Zweite entnommene Kugel schwarz.
![[Pasted image 20241226175037.png]]
$$
\begin{align}
&=\frac{5}{14}\cdot \frac{10}{15}+\frac{4}{14}\cdot \frac{5}{15} \\
&=\frac{1}{3}
\end{align}
$$
