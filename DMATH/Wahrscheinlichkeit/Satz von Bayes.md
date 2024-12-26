Wir betrachten als erstes den Fall von zwei komplementären [[Menge|Mengen]] $B$ und $\bar{B}$ für die gilt: $B\cup \bar{B}=\Omega$ und $B\cap \bar{B}=\emptyset$

Gegeben:
- $B, \bar{B} \subset \Omega$ (vollständige Zerlegung)
- $p(B),p(\bar{B})>0$
- Ein Ereignis $A$ mit $p(A)>0$

Dann gilt der **Satz von Bayes**
$$
p(B|A)=\frac{p(A|B)p(B)}{p(A)}
$$
Mit dem [[Satz der Totalen Wahrscheinlichkeit]] gilt:
$$
p(B|A)=\frac{p(A|B)p(B)}{p(A|B)p(B)+p(A|\bar{B})p(\bar{B})}
$$

## Allgemeiner Fall
>[!Theorem]
>Voraussetzungen:
>- $B_{1},,\dots B_{k} \subset \Omega$ eine vollständige Zerlegung von $\Omega$.
>- $p(B_{i})>0 \forall i$
>- Ereignis $A$ mit $p(A)>0$
>Dann gilt für jedes $j$:
>$$
>p(B_{j}|A)=\frac{p(A|B_{j})p(B_{j})}{p(A)}=\frac{p(a|B_{j})p(B_{j})}{\sum_{i=i}^{k}p(A|B_{i})p(B_{i})}
>$$

## Beispiel
