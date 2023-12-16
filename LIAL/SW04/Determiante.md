- Jede $n*n$ [[Matrizen|Matrix]] ist entweder **singulär** (nicht [[Invertierte Matrix|invertierbar]]) oder regulär (invertierbar)

## Definition
In der linearen Algebra ist die Determinante eine Zahl (ein Skalar), die einer quadratischen Matrix zugeordnet wird und aus ihren Einträgen berechnet werden kann. Sie ist ein nützliches Hilfsmittel bei der Lösung linearer Gleichungssysteme. Übliche Schreibweisen für die Determinante einer quadratischen Matrix $A$ sind $det(A)$, $detA$ oder $|A|$.

>[!info]
>Eine Matrix ist regulär, wenn ihre Determiante von 0 verschieden ist.
>Ist die Determinatne 0, so ist die Matrix singulär


## Determinante 2x2
$$ \left|\begin{pmatrix}
a & c \\
b & d
\end{pmatrix} \right| = (a*d) - (b*c)$$
![[Determinante.png]]
Die Zahlen auf dem roten Strich werde multipliziert und die Zahlen auf dem grünen Strich werden multipliziert und dem roten abgezogen.

## Determinante 3x3
Die Determinante einer 3x3-Matrix wird mit der [[Regel von Sarrus]] berechnet.


## Einfache Determinanten
* Determinante von Matrizen in Dreiecksgestalt -> Produkt der Diagonalen
* Vertauschen zweier Zeilen ändert das Vorzeichen.
* Multiplikation einer Zeile mit einem Faktor multipliziert die Determinate mit diesem Faktor
* Durch die Addition des Vielfachen einer Zeile zu einer anderen ändert sich die Determinante nicht.
* Beim [[Transponierte Matrix|Transponieren der Matrizen]] ändert sich die Determinante nicht; die oben genannte Regeln gelten auch für die Spalten.

## Weitere Aussagen
Sei $A$ eine quadratische $n \times n$-Matrix
* $A$ ist regulär
* $A^T$ ist regulär
* Die Determinante von $A$ ist nicht null.
* Der *Nullvektor* ist die einzige Lösung von $Ax=0$.
* Der Rang von $A$ ist gleich $n$.
