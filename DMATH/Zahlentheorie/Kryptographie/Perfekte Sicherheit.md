>[!Definition]
>Ein Verschlüsselungsalgorithmus ($M,C,K,f,f^{*}$) heisst **perfekt sicher**, falls für alle $m\in M$ und alle $c\in C$ folgendes gilt:
>$$
>p(m|c)=p(m)
>$$
>d.h. die Kenntnis von (irgend) eines Geheimtextes $c$ liefert (absolut) keine Information über das Vorliegen (irgend) eines Klartextes $m$. (Siehe [[Bedingte Wahrscheinlichkeit]]).



Ein Kryptosystem heisst perfekt sicher, fall die Ereignisse, dass ein bestimmter Geheimtext $c$ auftritt und ein bestimmter Klartext $m$ vorliegt, [[Unabhängige Ergeinisse|unabhängig]] sind. Es gilt $\forall c,\forall m(p(m|c)=p(m))$
- Falls $p(m|c)>p(m)$ für einen bestimmten Klartext $m$, könnte ein Angreifer beim Auftreten von $c$ mit grosser [[Wahrscheinlichkeit]] auf den Klartext $m$ schliessen.
- Falls $p(m|c)<p(m)$ für einen bestimmten Klartext $m$, könnte ein Angreifer beim Auftreten von $c$ schliessen, dass der Klartext $m$ unwahrscheinlich ist.

>[!Theorem]
>Sei $|M|=|C|=|K|<\infty$, d.h. Klartextmenge, Ciphermenge und Schlüsselmenge seien gleich gross und endlich und $\forall m\in M(p(m)>0)$, d.h. jeder Klartext kommt vor.
>Dann ist ein Verschlüsselungsverfahren genau dann perfekt sicher, falls:
>1. Alle Schlüssel sind gleich wahrscheinlich.
>2. Für jeden Klartext $m$ und jeden Geheimtext $c$ existiert genau ein Schlüssel $k$ mit $E(k,m)=c$
>Hier ist $E$ die Verschlüsselungsfunktion.



## Beispiele
**Beispiel 1**
Bei der [[Caesar Cipher]] werde jeder Schlüssel $k\in K=\mathbb{Z}_{26}$ mit gleicher Wahrscheinlichkeit ausgewählt. Dann wäre die Verschlüsselung **eines** Buchstabens perfekt sicher.

**Beispiel 2**
Gegeben sei die Klartextmenge $M = \{a, b\}$, die Geheimtextmenge $C = \{A, B\}$ und die Schlüsselmenge $K = \{0, 1\}$, sowie die Wahrscheinlichkeitsverteilungen auf der Klartextmenge $p(a) = 1/4, p(b) = 3/4$ und auf der Schlüsselmenge $p(0) = 1/4, p(1) = 3/4$.
Die Verschlüsselungsfunktion f sei wie folgt definiert:
$$
\begin{align}
f(0,a)&=A \\
f(0,b)&=B \\
f(1,a)&=B \\
f(1,b)&=A
\end{align}
$$

![[Pasted image 20241231091010.png]]

Untersuchen Sie das System auf perfekte Sicherheit. Bestimmen Sie p(A), p(B), $p(A|a)$, $p(A|b),$ $p(B|a)$ und $p(B|b).$
Verwenden Sie dann den [[Satz von Bayes]] um $p(a|A)$ zu berechnen und vergleichen Sie mit $p(a)$

$$
\begin{align}
p(a|A)&=\frac{p(A|a)p(a)}{p(A)} \\
&=\frac{p(A|a)\cdot \frac{1}{4}}{p(A)}
\end{align}
$$
Nun müssen wir noch $(A|a)$ herausfinden sowie, $p(A)$
![[Pasted image 20241231091756.png]]
Aus diesem Baum folgt:
1. $p(A|a) = \frac{1}{4}$
2. $p(A)=\frac{3}{4}\cdot \frac{3}{4}+\frac{1}{4}\cdot \frac{{1}}{4}=\frac{10}{16}$
=>
$$
\begin{align}
p(a|A)&=\frac{p(A|a)p(a)}{p(A)} \\
&=\frac{\frac{1}{4}\cdot \frac{1}{4}}{\frac{10}{16}} \\
&=\frac{1}{16} \cdot \frac{16}{10} \\
&=\frac{1}{10}
\end{align}
$$
$\implies p(a|A)\neq p(a) \to \frac{1}{10}\neq \frac{1}{4}$
