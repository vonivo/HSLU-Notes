Ein in [[Polarkoordinaten]] gegebene [[Kurve]] $\gamma$ wird durch folgende Abbildung spezifiziert:
$$
\gamma:[\alpha, \beta] \to \mathbb{R}, \phi \mapsto r=r(\phi)
$$
Jedem Winkel $\phi \in [\alpha, \beta]$ wird der Abstand der Kurve $r=r(\phi)$ vom Ursprung zugeordnet.

>[!warning]
>Alle Winkel werden von der positiven $x$-Achse aus im Gegenuhrzeigersinn gemessen. Hier $\alpha\lt0$ und $\beta\gt 0$.

## Ableiten einer Kurve in Polarkoordinaten
Die [[Ableitung]] wird bestimmt, indem man die Polarkoordinaten in Parameterform bringt:
$$
\begin{align}
x &= x(\phi) = r(\phi)\cos \phi \\
y &= y(\phi) = r(\phi) \sin \phi
\end{align}
$$
Hier ist $\phi$ der Parameter der Kurve. Dann wird die bereits bekannte Formel von [[Ableiten einer Kurve]] weitergearbeitet:
$$
y'(x) = \frac{dy}{dx} = \frac{\frac{dy}{d\phi}}{\frac{dx}{d\phi}} = \frac{\dot{r}(\phi)\sin(\phi)+r(\phi)\cos \phi}{\dot{r}(\phi)\cos \phi-r(\phi)\sin \phi}
$$
