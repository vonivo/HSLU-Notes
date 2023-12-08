Eine $A\in\mathbb{R}^{l*m}$ [[Matrizen|Matrix]] mit L Zeilen und m Spalten kann mit einer Matrix $B\in\mathbb{R}^{m*n}$
multipliziert werden. Das Produkt $AB = C \in\mathbb{R}^{l*n}$

Bsp:
$$
\begin{pmatrix} 
  a & b & c \\  
  d & e & f
\end{pmatrix} * 
\begin{pmatrix}
g & h \\
i & j \\
k & l
\end{pmatrix} = \begin{pmatrix}
a*g + b*i + c*k & a*h + b*j + c*l \\
d*g + e*i + f*k & d*h + e*j + f*l
\end{pmatrix}$$
## Eigenschaften
* Die Anzahl der Spalten der ersten Matrix muss gleich der Anzahl Zeilen der zweiten Matrix sein.
* Das Produkt $C = AB$ hat soviele Zeilen $(l)$ wie $A$ und soviele Spalten wie $(n)$ wie $B$.
* Das Element in der i-ten Zeile und der K-ten Spalte von C ist das Skalarprodukt der i-ten Zeile von A mit der k-ten Spalte von B.
* Bei der Matrixmultiplikation spielt die Reihenfolge der Faktoren eine Rolle: $AB\neq BA$
* Die Matrixmultiplikation ist assoziativ:
$$(AB)C=A(BC)=ABC$$

