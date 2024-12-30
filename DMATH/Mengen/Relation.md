>[!Definition]
>Eine Relation $R$ auf einer [[Menge]] ist eine Teilmenge von $A\times A$.

**Beispiel 1**
Sei $A$ die Menge aller Landpunkte eines virtuellen Planeten. Dann ist $A\times A = \{ (x,y)|x\in A\land y\in A \}$

Wir definieren die Relation $R$ auf $A$:
$$
R=\{ (x,y) \in A\times A|y \text{ lässt sich von x aus trockenen fusses erreichen} \}
$$
-> $x,y$ liegen auf derselben Insel.

**Beispiel 2**
Für ein $n\in \mathbb{N}\text{\\}\{0\}$ betrachten wir die folgende Relation auf $\mathbb{Z}$ ([[Kongruenz modulo n]])
$$
R=\{ (x,y)\in \mathbb{Z}\times \mathbb{Z}|y\equiv x \text{ mod n} \}
$$

Diese Relation erfüllt für $n=11$ z.B. $(2,13)$

## Reflexivität
>[!Definition]
>Eine Relation $R$ auf der Menge $A$ heisst **reflexiv,** falls gilt $\forall x\in A((x,x)\in R)$

**Beispiel 1**
Die Relation auf der Menge der Landpunkte $A$ der virtuellen Planente ist reflexiv, denn jeder Landpunkt lässt sich selbst trockenen Fußes erreichen, wenn man schon dort ist.
=> $\forall x \in A((x,x)\in R)$

**Beispiel 2**
Die Relation $R=\{ (x,y)\in \mathbb{Z}\times \mathbb{Z}|y\equiv x \text{ mod n} \}$ ist reflexiv da:
$$
\forall x | x\equiv x\text{ mod }n
$$

## Symmetrie
>[!Definition]
>Eine Relation $R$ ist symmetrisch auf der Menge $A$ falls gilt:
>$\forall x,y \in A((x,y)\in R\to(y,x)\in R)$

**Beispiel 1**
Die Relation der Landpunkte ist symmetrisch, da jeder Landpunkt $y$ der von Landpunkt $y$ aus trockenen Fusses erreichbar ist auf dem umgekehrten Weg von $y$ nach $x$ auch erreichbar ist.
=> $\forall x,y \in A ((x,y)\in R \to (y,x) \in R)$

**Beispiel 2**
Auch die Relation $R=\{ (x,y)\in \mathbb{Z}\times \mathbb{Z}|y\equiv x \text{ mod n} \}$ ist symmetrisch da:
$$
\begin{align}
x&\equiv y \text{ mod }n \\
y&\equiv x \text{ mod  }n
\end{align}
$$
## Transitivität
>[!Definition]
>Eine Relation $R$ der Menge $A$ heisst transitive, falls:
>$\forall x,y,z(()(x,y)\in R \land(y,z)\in R) \to (x,z)\in R)$

**Beispiel 1**
Die Relation auf der Menge der Landpunkte ist Transitiv, denn für je 3 Landpunkte $x,y,z$ gilt: Lässt sich $y$ von $x$ aus trockenen Fusses erreichen und $z$ von $y$ aus, sind alle Punkte auf derselben Inseln. Dementsprechend lässt sich au $z$ von $x$ aus erreichen.

**Beispiel 2**
Auch die Relation $R=\{ (x,y)\in \mathbb{Z}\times \mathbb{Z}|y\equiv x \text{ mod n} \}$ ist transitiv da:
$$
\begin{align}
x&\equiv y \text{ mod }n \\
y&\equiv z \text{ mod n} \\
\implies x&\equiv z \text{ mod  }n
\end{align}
$$
Dies lässt sich beweise durch:
$$
\begin{align}
y &= kn+x \\
z&=k_{1}n+y \\
\implies z&=k_{1}n+(kn+x) \\
&=x+n(k_{1}+k)
\end{align}
$$
## Äquivalenzrelation
>[!Definition]
>Eine Relation $R$ auf der Menge $A$ heisst Äquivalenzrelation, falls sie **relfexiv, symmetrisch und transitiv** ist.

**Beispiel 1**
Ist symmetrisch, reflexiv und transitiv und somit eine **Äquivalenzrelation**.

**Beispiel 2**
Ist symmetrisch, reflexiv und transitiv und somit eine **Äquivalenzrelation**.

>[!Theorem]
>Eine Äquivalenzrelation auf der Menge $A$ zerlegt diese Menge in **disjunkte**, **nicht leere** Teilmengen, genannt Äquivalenzklassen. Dabei sind zwei Elemente ein und derselben Äquivalenzklasse äquivalent, je zwei Elemente verschiedener Äquivalenzklassen nicht äquivalent.

**Beispiel 1**
Diese Relation zerlegt Menge $A$ in alle Inseln -> Die Inseln sind die Äquivalenzklassen.

**Beispiel 2**
Die Äquivalenzklassen werden hier mit $[0],[1],\dots,[n-1]$ bezeichnet. Dabei enthält $[r]$ alle Zahlen $x\in\mathbb{Z}$ für die gilt: $x\equiv r \text{ mod }n$.
