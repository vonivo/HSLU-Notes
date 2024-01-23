* Die [[Matrizen|Rotationsmatrix]] wird mit dem [[Vektoren|Vektor]] multipliziert ([[Vektormulitpliaktion]]).
* Der Nullvektor wird auf sich selbst [[Lineare Abbildung|abgebildet]].
* Die Abbildung ist lienar
* Rotationen sind [[Orthogonale Matrix|orthogonal]] und haben eine [[Determinante]] von $+1$.

## Beispiel
$$
\begin{pmatrix}
\cos(\varphi) & -\sin(\varphi)\\
\sin(\varphi) & \cos(\varphi) 
\end{pmatrix} * \begin{pmatrix}
x \\
y
\end{pmatrix} = \begin{pmatrix}
x\cos(\varphi) & y-\sin(\varphi)\\
x\sin(\varphi) & y\cos(\varphi) 
\end{pmatrix}
$$

Um an einer bestimmten Achse zu spiegeln, muss zuerst die Spiegelchachse in die Y-Ache mittels einer [[Translation]] überführt werden.
Selbes gilt für eine Rotation. Da muss zuerst an den 0-Punkt (Drehpunkt) verschoben werden