Die *Strecke* zwischen zwei Punkten $x_{1}\in \mathbb{R}^{n}, x_{2} \in \mathbb{R}^{n}$ ist die Menge $\{ x\in\mathbb{R}^{n}:x=\lambda x_{1}+(1-\lambda)x_{2}$ für $0\leq \lambda\leq 1\}$.
![[Strecke_zwischen_Punkte.png]]
>[!Definition]
>Eine Menge $S\subseteq \mathbb{R}^{n}$ ist **konvex**, falls für jedes Paar von zwei Punkten $x_{1}\in S, x_{2}\in S$ die Strecke zwischen ihnen ganz in $S$ enthalten ist:
>
>für jedes $x_{1}\in S,x_{2}\in S$ und $0\leq \lambda\leq 1$ gilt $x := \lambda x_{1}+(1-\lambda)x_{2} \in S$.

![[KonvexeHülle.png]]
## Eigenschaften
Falls $S_{1}$ und $S_{2}$ zwei **konvexe Mengen** sind, dann sind auch folgende Mengen Konvex:
- $S = S_{1}\cap S_{2}$
- $S = S_{1}+S_{2}=\{ x_{1}+x_{2}|x_{1}\in S_{1}, x_{2} \in S_{2} \}$ (Minkowski-Summe)
