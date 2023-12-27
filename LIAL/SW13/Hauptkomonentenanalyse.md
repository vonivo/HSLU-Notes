Wir nehmen an, $\tilde{X}$ sei eine [[Matrizen]|Datenmatrix] mit $m$ Zeilen (die Samples) und $n$ Spalten (die einzelnen Variablen).
Beispielsweise:
- Für jede von $m$ Personen werden $n=3$ Merkmale, wie Grösse, Gewicht und Alter gemessen

Nun wird diese Matrix mithilfe der [[Zentrierende Matrix|zentrierenden Matrix]] $M$ zentriert.
$$
X = M\tilde{X}
$$
>[!warning]
>Die Datenmatrix $\tilde{X}$ muss zwingend zentriert werden. Nur dann ist die Kovarianzmatrix gegben.

Nun kann die Kovarianzmatrix $C$ bestimmt werden.
$$
C = \frac{1}{m-1}X^TX
$$
## Eigenschaften der Kovarianzmatrix
- Falls $X$ eine $m \times n$-Matrix ist, dann ist die Kovarianzmatrix $C$ eine $n \times n$-Matrix.
- Die Kovarianzmatrix enthält auf der Diagonale die Varianzen (Streuung) der $n$ Variablen.
- Die Kovarianzmatrix ist [[Symmetrische Matrix|symmetrisch]] und enthält in den Elementen neben der Diagonale die Kovarianzen von zwei Variablen
	- Ist die Kovarianz $C_{i,j}$ Null, dann sind die beiden Variablen $i$ und $j$ nicht korreliert.
	- Ist die Kovarianz $C_{i,j}$ grösser als Null, dann bedeutet eine Zunahme der Variable $i$ auch eine Zunahme der Variable $j$.
	- Ist die Kovarianz $C_{i,j}$ kleiner als Null, dann bedeutet eine Zunahme der Variable $i$ auch eine Abnahme der Variable $j$.

## Eigenschaften mit [[Eigenwerte und Eigenvektoren|Eigenwertzerlegung]]
Die [[Eigenwerte und Eigenvektoren|Eigenwertzerlegung]] der Kovarianzmatrix
$$
C = V\Lambda V^T
$$
liefert in der Eigenvektormatrix $V$ von $C$ die Hauptachsen/-richtungen (principal direction/-axes).

Die Kovarianzmatrix ist symmetrisch und positiv semidefinit, daher sind alle Eigenwerte nicht negativ. Die Eigenvektoren (Spalten von $V$) sidn paarweise orthogonal und können normiert werden.

Die Eigenwerte in $\Lambda$ sind die Varianzen im gedrehten Koordinatensystem (welches als Achsen die Eigenvektoren hat) und sie werden der Grösse nach (absteigend) sortiert. Daraus ergibt sich auch die Ordnung der Hauptachsen, d. h. Eigenvektoren in $V$.
- Der Eigenvektor zum grössten Eigenwert ist die **1. Hauptachse** und zeigt in Richtung der grössten Varianz.
- Der Eigenvektor zum zweitgrössten Eigenwert ist die **2. Hauptachse** und steht senkrecht auf der **1. Hauptachse** und zeigt in Richtung der zweitgrössten Varianz.

## Eigenschaften mit [[Singulärwertzerlegung]]
Mann kann auch die SVD der $m \times n$-Matrix $X$ verwenden: $X=U\Sigma V^T$. Dann gilt:
$$
\begin{align}
C &= \frac{1}{m-1}X^TX \\
&=\frac{1}{m-1}(U\Sigma V^T)^TU\Sigma V^T \\
&=\frac{1}{m-1}(V^T)^T\Sigma^TU^TU\Sigma V^T \\
&=\frac{1}{m-1}V\Sigma^TU^TU\Sigma V^T \\
&=\frac{1}{m-1}V\Sigma^2 V^T  \\
&=V\frac{\Sigma^2}{m-1}V^T
\end{align}
$$
- Falls $X=U\Sigma V^T$ dann sind die Spalten von $V$ die **Hauptachsenrichtungen**. Die Spalten von $U\Sigma=XV$ sind die **Hauptachsenkomponenten**
- Die Singulärwerte $\sigma_i$ stehen mit den Eigenwerten $\lambda_i$ der Kovarianzmatrix $C$ in der Beziehung $\lambda_i=\frac{\sigma_i^2}{m-1}$. Die Eigenwerte $\lambda_i$ entsprechen den **Varianzen der entsprechenden Hauptachsenkomponenten**.
- Will man die Dimensionalität der Daten von $n$ auf $k\lt n$ reduzieren, dann
	- werden die ersten $k$ Spalten von $U$ (oder $V$) verwendet
	- die $k \times k$-Submatrix oben links von $\Sigma$.
	Dann ist deren Produkt $U_k\Sigma_k$ die reduzierte Datenmatrix, bestehend aus den ersten $k$ **Hauptkomponenten** (principal components, PC).