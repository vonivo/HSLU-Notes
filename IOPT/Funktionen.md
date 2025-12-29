## [[Lineare Funktion]]
Eine Funktion $f:\mathbb{R}^{n}\to \mathbb{R}$ ist linear, falls $f$ die Form $f(x)=cx+d$ hat, $c\in\mathbb{R}, d\in \mathbb{R}$

### Eigenschaften
- Eine Lineare Funktion ist sowhol **konvex als konkav.**

## [[Krümmungsverhalten#Konvex|Konvexe Funktion]]
Sei $S\subseteq \mathbb{R}^{n}$ ein [[Konvexe Menge|konvexe Menge]].

Eine Funktion $f:S\to \mathbb{R}$ ist konvex auf $S$ falls:
$$
f(\lambda x_{1}+(1-\lambda )x_{2}) \leq \lambda f(x_{1})+(1-\lambda)f(x_{2})
$$
für alle $x_{1},x_{2} \in S$ und $0\leq \lambda\leq 1$.
![[IOPT/img/Konvex.png]]
### Eigenschaften
- $f$ ist konvex genau falls $g := -f$ kokav ist.

## [[Krümmungsverhalten#Konkav|Konkave Funktion]]

Sei $S\subseteq \mathbb{R}^{n}$ ein [[Konvexe Menge|konvexe Menge]].

Eine Funktion $f:S\to \mathbb{R}$ ist konkav auf $S$ falls:
$$
f(\lambda x_{1}+(1-\lambda)x_{2})\geq \lambda f(x_{1})+(1-\lambda)f(x_{2})
$$
für alle $x_{1},x_{2} \in S$ und $0\leq \lambda\leq 1$.
![[IOPT/img/Konkav.png]]
### Eigenschaften
- $f$ ist konvak genau falls $g := -f$ konvex ist.