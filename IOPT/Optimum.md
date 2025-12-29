## Globales Optimum
Sei ein [[IOPT/Optimierungsproblem|Minimierungsproblem]] $f(x)$ unter der Bedingungen $x \in S$.

>[!Definition]
>Falls $x^{*} \in S$ und $f(x^{*}) \leq f(x)$ für alle $x \in S$, dann ist $x^{*}$ eine **global optimale Lösung**, also ein **globales Optimum**.
![[globalesOptimum.png]]
## Lokales Optimum
Eine $\epsilon$-Nachbarschaft eines Punktes $x \in \mathbb{R}^{n}$ ist die Menge $N_{\epsilon}(x)=\{y\in\mathbb{R}^{n}: \mid\mid y-x\mid\mid<\epsilon\}$.

=> $\mid\mid a\mid\mid$ bezeichnet die (euklidische) Norm von $a$: $\mid\mid a\mid\mid=(a_{1}^{2}+a_{2}^{2}+\dots+a_{n}^{2})^{1/2}$.

>[!Definition]
>Falls $x^{*}\in S$ und es existiert eine $\epsilon$-Nachbarschaft $N_{\epsilon(x^{*})}$ so dass $f(x^{*})\leq f(x)$ für alle $x\in N_{\epsilon}(x^{*}) \cap S$, dann ist $x^{*}$ eine **lokal optimale Lösung**, ein **lokales Optimum**.

![[lokalesOptimum.png]]

