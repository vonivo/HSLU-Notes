Ein Quantor ist ein Angabe über die Quantität der Elemente für die ein [[Prädikat]] whar ist.

Wird eine  Quantor auf $x$ angewandt, nennt man diese Variable gebunden.
# Allquantor
>[!Info]
>Ist $P(x)$ ([[Prädikat]]) wahr für alle $x$ aus einer bestimmten Universalmenge, dann schreibt mann $\forall xP(x)$ und liest: "für alle $x$ gilt $P(x)$"

## Beispiel
Prädikat: $x+1\gt x$
Dann sieht man sofort, dass $\forall xP(x)$ gilt.

Steht $Q(x)$ für $x<2$ gilt sicherlich nicht $\forall xQ(x)$, sondern $\neg\forall q(x)$.


# Existenzquantor
>[!Info]
>Ist $P(x)$ wahr für mindestens ein $x$ aus einer bestimmten Universalmenge, dann schreibt man $\exists xP(x)$ und liest: "es existiert ein $x$ für welches $P(x)$ wahr ist".

Falls **genau ein** Element existiert schreibt man $\exists!xP(x)$.

## Beispiel
Für das [[Prädikat]] $P(x)=x\gt 2$ gilt sicher $\exists xP(x)$.
Und für das $Q(x)=x>2\land x<4$ gilt $\exists!xQ(x)$ denn nur $3$ erfüllt dieses Prädikat.

# Rechenregeln

| Aussage              | ist äquivalent zu    | Aussage ist wahr                                | Aussage ist falsch                           |
| -------------------- | -------------------- | ----------------------------------------------- | -------------------------------------------- |
| $\neg \exists xP(x)$ | $\forall x\neg P(x)$ | für alle $x$ ist $P(x)$ falsch                  | Es gibt ein $x$ für welches $P(x)$ wahr ist. |
| $\neg \forall xP(x)$ | $\exists x\neg P(x)$ | Es gibt ein $x$, für welches $P(x)$ falsch ist. | $P(x)$ ist wahr für alle $x$.                |
## Reihenfolge
Schreibe die Negation der folgende Prädikate ohne Negationszeichen:
$$
\forall x\exists y(xy=1)¹
$$
Lösung:
$$
\begin{align}
\neg\forall x\exists y(xy=1) &\equiv \exists x\neg(\exists y(xy=1)) \\
&\equiv \exists x\forall y(\neg(xy=1)) \\
&\equiv \exists x\forall y(xy\neq 1)
\end{align}
$$
