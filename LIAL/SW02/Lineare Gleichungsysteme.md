## Definition Gleichungssystem
Ein Gleichungssystem besteht aus mehreren Gleichungen die alle gemeinsam erfüllt sein müssen.

### Lineare Gleichungssysteme
- Auf einer Seite kommen keine Variablen, sondern nur Konstanten vor.
- Auf der anderen Seite stehen, Summen, die aus Produkten jeweils einer Variablen mit einem konstanten Faktor, auch Koeffizient, genannt besteht.
- Die Variablen kommen nur in erster Potenz vor.

Das Gleichungssystem [[Matrizen]]
$$ \left \{ 
	\begin{align} 
	6x + &2y - z &= 4 \\ 
	x+y+10z&=-6
	\end{align} 
\right. $$kann wie folgt in [[Matrizen]] notiert werden;
$$\begin{pmatrix}6  & -1& -1 \\ 1 & 1 &10 \end{pmatrix} *\begin{pmatrix}x \\ y\\z \end{pmatrix} = \begin{pmatrix}4\\-6\end{pmatrix}$$
Dabei nennt man die erste [[Matrizen|Matrix]] **Koeffizientenzmatrix**.

Schreibt man die Koeffizienten auf der linke und rechten Seite des Gleichungssystems in einer Matrix, spricht man von der erweiterten Koeffizientenmatrix:
$$
  \left(\begin{array}{rrr|r}
    6 & -1 & -1 & 4 \\
    1 & 1 & 10 & -6
  \end{array}\right)
$$