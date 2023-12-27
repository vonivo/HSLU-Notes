Die $n \times n$-[[Matrizen|Matrix]] $A$ hat nur dann ein [[Invertierte Matrix|Inverse]] $A^{-1}$, falls die Matrix $A$ regulär ist, d. h. den [[Rang einer Matrix|Rang]] n hat und eine [[Determinante]] verschieden von null.

Die **Moore-Penrose-Pseudoinverse** ist die beste Inverse einer beliebigen $m \times n$-Matrix $A$.

## Theorem
1. $AA^{+}A = A$      d. h. $AA^{+}$ bildet die Spalten von A auf sich ab.
2. $A^{+}AA^{+}=A^{+}$ 
3. $(AA^{+})^T=AA^{+}$   d. h. $AA^{+}$ ist [[Symmetrische Matrix|symmetrisch]].
4. $(A^{+}A)^T = A^{+}A$   d. h. $A^{+}A$ is [[Symmetrische Matrix|symmetrisch]].
Ist $A=U\Sigma V^T$ die SVD von A, dann gilt $A^{+} = V\Sigma^{+}U^T$ wobei $\Sigma^{+}$ auf der Diagonalen die **Kehrwerte der [[Singulärwertzerlegung|Singulärwerte]]** enthält: $\frac{1}{\sigma_{i}}, \frac{1}{\sigma_{2}}\dots, \frac{1}{\sigma_{r}}$ (wobei $r=\operatorname{rang}(A)$)
