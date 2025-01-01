Null-Eins Matrizen sind [[Matrizen]] welche nur aus Nullen und Einsen bestehen. Sie werden auch bei [[AD/Algorithmen/Graphen/Graph|Graphen]] verwendet.

## Und/Oder Operation
Die **Und/Oder**-Verknüpfung zweier $(n\times m)$-Matrizen $A$ und $B$ wird definiert durch:
$$
A\lor B=[a_{i,j}\lor b_{\mathrm{i,j}}]
$$
und
$$
A\land B=[a_{i,j}\land b_{i,j}]
$$
### Beispiel
$$
\begin{align}
A&=\begin{bmatrix}
1 & 0 & 1 \\
0 & 1 & 0
\end{bmatrix} \\
B&=\begin{bmatrix}
0 & 1 & 0 \\
1 & 1 & 0
\end{bmatrix} \\
A\lor B&=\begin{bmatrix}
1 & 1 & 1 \\
1 & 1 & 0
\end{bmatrix} \\
A\land B&=\begin{bmatrix}
0 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix}
\end{align}
$$
## Boolsches Produkt
>[!Definition]
>Das **boolsche Produkt** der $(m\times n)$-Matrix $A=[a_{i.,j}]$ mit der $(n\times p)$-Matrix $B=[b_{i,j}]$ wird definiert durch:
>$$
>A\odot B = [c_{i,j}]\text{, wobei } c_{i,i}=(a_{i,j}\land b_{1,j})\lor(a_{i,2}\land b_{2,j})\lor\dots \lor(a_{i,n}\land b_{n,j})
>$$
>mit $1\leq i\leq m$ und $1\leq j\leq n$.

=> Funktioniert wie bei der [[Matrixmultiplikation]] einfach mit den boolschen Operationen.
### Beispiel
$$
\begin{align}
A&=\begin{bmatrix}
1 & 0 \\
0 & 1 \\
1 & 0
\end{bmatrix} \\
B&=\begin{bmatrix}
1 & 1 & 0 \\
0 & 1 & 1
\end{bmatrix} \\
A\odot B&=\begin{bmatrix}
(1\land1)\lor(0\land0) & (1\land 1)\lor(0\land 1) & (1\land0)\lor(0\land{1}) \\
(0\land1)\lor(1\land0) & (0\land 1)\lor(1\land 1) & (0\land0)\lor(1\land{1}) \\
(1\land1)\lor(0\land0) & (1\land 1)\lor(0\land 1) & (1\land0)\lor(0\land{1})
\end{bmatrix} \\
&=\begin{bmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 1 & 0
\end{bmatrix}
\end{align}
$$

## r-te Boolsche Potenz
>[!Definition]
>die r-te boolsche Potenz der **quadratischen** $(n\times n)$-Matrix $A$ ist definiert durch:
>$$
>A^{(r)}=A\odot A\odot \dots\odot A\text{, wobei } A^{[0]}=1_{n}\text{ verwendet wird} 
>$$
