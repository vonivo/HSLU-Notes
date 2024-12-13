Die Kurve ist ähnlich einer [[ANLIS/SW01/Funktionen/Funktion]] jedoch kann sie mehrere **Variablen** besitzen.
Neben der Form $y=f(x)$ kann man Kurven auch in der **Parameterform** beschreiben. Jedem Wert des Parameters $t$ wird dabei ein Punkt $\vec{x}(t)$ in der Ebenen (oder auch im Raum) zugeordnet. Man nennt dies auch **Parameterdarstellung** , der Kurve, welche gleich ist wie die Schreibweise eines [[Vektoren]] ist.

![[Kurve.png]]
Die Kurve $\gamma$ ist eine Abbildung der Form
$$
\gamma:[a,b] \to \mathbb{R}^2, t \mapsto \vec{x}(t) = \begin{bmatrix}
x(t)  \\
y(t)
\end{bmatrix}
$$
Für $t=a$ ist man am Anfang der Kurve, für eine beliebiges $t \in [a,b]$ an der Stelle $\vec{x}(t)$ und für $t = b$ am Ende der Kurve.

Für jeden Punkt $\vec{x}$ auf der Kurve gibt es genau ein $t\in[a,b]$, sodass $\vec{x}(t) = \vec{x}$, und auch die Umkehrung gilt.

## Beispiel Ellipse
Die Parameterform einer Ellipse sieht wie folgt aus:
$$
\vec{x}(t) = \begin{bmatrix}
A \cos(t) \\
B \sin(t)
\end{bmatrix}
$$
Wobei $A$ und $B$ die Halbachsen der Ellipse darstellen.