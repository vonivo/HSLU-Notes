Die reelle [[Symmetrische Matrix|symmetrische Matrix]] $A$ ist positiv definit, falls $x^TAx > 0$ für alle $x \ne 0$. Man nennt sie positiv semi-definit, falls der obige Ausdruck grösser gleich null ist.
$$
x^TAx = \begin{bmatrix}
x_{1}  & x_{2}
\end{bmatrix}\begin{bmatrix}
1 & 2 \\
2 & 4
\end{bmatrix}\begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix} = x_{1}^2+4x_{1}x_{2}+4x_{2}^2 = (x_{1}+2x_{2})
$$


## Beispiel
$A = \begin{bmatrix}1 & 2 \\2 & 4\end{bmatrix}$ ist nicht positiv definit, denn für $x_{1} = -2, x_{2} = 1$ ist $(x_{1}+2x_{2})^2 = 0$

## Eigenschaften
Die Eigenwerte einer reellen, [[Symmetrische Matrix|symmetrischen]], positiv definiten [[Matrizen]] sind reell und positiv.

## Link zur [[Lineare Regression|linearen Regression]]
Falls $A$ linear unabhängige Spalten hat, dann ist $A^TA$ eine symmetrische, positiv definite Matrix.
$$
A = \begin{bmatrix}
1 & 1 \\
1 & 2 \\
1 & 2
\end{bmatrix}
$$

