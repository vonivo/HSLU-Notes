Eine Lineare ist die Abblidung einer Matrix zu verschieden [[Einheitsvektoren]].
![[Pasted image 20231218123308.png]]
Die Einheitsvektoren symbolisieren die rot und blauen Pfeile.

Der Buchstabe F wird durch folgende Matrix aufgespannt:
$$
\begin{pmatrix}
1 & 2 & 2 & 3 & 3 & 2 & 2 & 4 & 4 & 1 \\
1 & 1 & 2 & 2 & 3 & 3 & 4 & 4 & 5 & 5
\end{pmatrix}
$$
Schreibt man nun beide Einheitsvektoren spaltenweise nacheinander erhät man die Transformations-Matrix $A$.

Bild Links:
$$
A = \begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$
Bild Rechts:
$$
A = \begin{pmatrix}
2 & 0 \\
0 & 2
\end{pmatrix}
$$
Um eine Abbildung zu transformieren muss nun die Abbildungsmatrix von links an die [[Matrizen|Matrix]] [[Matrixmultiplikation|multipliziert]] werden.
$$
\begin{pmatrix}
2 & 0 \\
0 & 2
\end{pmatrix}
\begin{pmatrix}
1 & 2 & 2 & 3 & 3 & 2 & 2 & 4 & 4 & 1 \\
1 & 1 & 2 & 2 & 3 & 3 & 4 & 4 & 5 & 5
\end{pmatrix}
$$
Nach dieser Rechnung erhält man die Transformation.

## Skalierung um den Faktor $a$.
$$A = a *\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}$$
## Drehung
Die Abbildung kann auch um $\phi$ Grad gedreht werden:
$$
A = \begin{pmatrix}
	\cos(30) & -\sin(30) \\
	\sin(30) & \cos(30)
\end{pmatrix}
$$

Mit dieser Abbildungsmatrix wird die Abbildung um 30° am Ursprung gedreht.

## Achsenspiegelung
Die Abbildung kann auch an einer Koordinaten-Achse gespiegelt werden.
### x-Achse
$$
A = \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
$$
### y-Achse
$$
A = \begin{pmatrix}
-1 & 0 \\
0 & 1
\end{pmatrix}
$$

## Zusammengesetzte Abbildungen

