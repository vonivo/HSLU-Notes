## Vektoren
Um einen [[Vektoren|Vektor]] orthogonal auf einen anderen zu projizieren (was auch beim [[Vektormulitpliaktion|Skalarprodukt]] gemacht wird) braucht es eine [[Matrizen|Projektionsmatrix]].
![[Orthogonale_Projektion.png]]
Um $\vec{b}$ auf $\vec{a}$ zu projizieren braucht es eine Projektionsmatrix $P$, sodass $P \vec{b} = b_{a}$.
Die Projektionsmatrix definiert sich wie folgt:
$$
b_{a} = b_{a}\frac{1}{|| \vec{a}||}\vec{a} = ||\vec{b}||\cos(\phi)\frac{1}{|| \vec{a}||}
$$
$$
	\begin{align} 
	b_{a} &= b_{a}\frac{1}{|| a||}a \\
    &=||b||\cos(\phi)\frac{1}{|| a||}a \\
   &=||b||\space||a||\cos(\phi)\frac{1}{|| a^2||}a \\
&=a^T b \frac{1}{|| a^2||}a \\
&=a^T b \frac{1}{a^Ta}a \\
&= \frac{a^T b}{a^Ta}a \\
&= \frac{1}{a^Ta}aa^T b = Pb
	\end{align} 
$$
$$
P = \frac{1}{a^Ta}aa^T
$$
## Projektion auf einen Spaltenraum
Falls die Spalten von X linear unabhängig sind lässt sich die [[Symmetrische Matrix]] $X^TX$ invertieren und man bekommt die Lösung für die [[Orthogonale Projektionen|Projektions- oder Prädiktionsmatrix]] $P$.
$$
P = X(X^TX)^{-1}X^T
$$

