Um [[Rotation|Rotationen]] und [[Translation|Translationen]] in ein einheitliches System zu bringen, existieren homogene Koordinaten.

Um dies zu bewerkstelligen wird einfach eine Dimension hinzu und die [[Matrizen|Abbildungsmatrix]] wird um eine Spalte und eine Zeile erweitert.

## Beispiel für die Rotation
Der Vektor:
$$
\vec{x}=\begin{pmatrix}
x \\
y
\end{pmatrix}
$$
soll um den Winkel $\varphi$ rotiert werden.

Die "Normale" [[Lineare Abbildung|Abbildungsmatrix]] würde nun so aussehen:
$$
\begin{pmatrix}
\cos(\varphi) & -\sin(\varphi)\\
\sin(\varphi) & \cos(\varphi) 
\end{pmatrix} * \begin{pmatrix}
x \\
y
\end{pmatrix}
$$
In homogenen Koordinaten sieht das ganze nu so aus:
$$  \left(\begin{array}{rr|r}
\cos(\varphi) & -\sin(\varphi) & 0\\
\sin(\varphi) & \cos(\varphi) & 0 \\ \hline
0 & 0 & 1 
  \end{array}\right) *\begin{pmatrix}
x \\
y \\
1
\end{pmatrix}
$$

## Beispiel für eine Translation
Der Vektor:
$$
\vec{x}=\begin{pmatrix}
x \\
y
\end{pmatrix}
$$
soll um den Vektor $(u,v)^T$ verschoben werden.

$$
 \left(\begin{array}{rr|r}
1 & 0 & u \\
0 & 1 & v \\ \hline
0 & 0 & 1 
  \end{array}\right) * \begin{pmatrix}
x \\
y \\ \hline
1
\end{pmatrix}
$$

