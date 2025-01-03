>[!Definition]
>Ein **aufspannender Wald** von einem [[DMATH/Graphen/Graph|Graph]] $G=(V,E)$ ist ein Teilgraph $G$ ohne Kreise, der alle Knoten von $G$ enthält.
>Ein aufgespannter Wald heisst minimal, wenn $w(T)\leq w(T')$ für jeden aufspannenden Wald $T'$ gilt.


![[Pasted image 20250103101404.png]]
Der Algorithmus von Kruskal berechnet einen sogenannten minimalen aufspannenden Wald $T$ von $G$ und die Menge $R$ der Zusammenhangskomponenten von $G$. Dabei wird ein Greedy-Algorithmus verwendet.

## Algorithmus
### Initialisierung
$$
\begin{align}
R & :=\{ \{ x \}\in V \} \\
T & := \emptyset
\end{align}
$$
### Ablauf
1. Wähle eine Kante $\{ x,y \}\in E-T$ minimalen Gewichts, sodass $x$ und $y$ nicht zur gleichen Klasse von $R$ gehören.
2. Ersetze in $R$ die beiden Klassen von $x$ und $y$ durch ihre Vereinigung.
3. Füge der Menge $T$ die Kante $\{ x,y \}$ hinzu.
4. Wiederhole solange $E-T=\emptyset$.

**Initialisierung**
![[Pasted image 20250103101807.png]]
$$
\begin{align}
R & :=\{ \{ a \},\{ b \},\{ c \},\{ d \},\{ e \},\{ f \},\{ g \},\{ h \},\{ i \},\{ j \},\{ k \} \} \\
T & := \emptyset
\end{align}
$$
**Schritt 1**
![[Pasted image 20250103102017.png]]
$$
\begin{align}
R & :=\{ \{ a,b \},\{ c \},\{ d \},\{ e \},\{ f \},\{ g \},\{ h \},\{ i \},\{ j \},\{ k \} \} \\
T & := \{ \{ a,b \} \}
\end{align}
$$
**Schritt 2**
![[Pasted image 20250103102115.png]]
$$
\begin{align}
R & :=\{ \{ a,b \},\{ c \},\{ d \},\{ e \},\{ f \},\{ g \},\{ h \},\{ j \},\{ i, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \} \}
\end{align}
$$
**Schritt 3**
![[Pasted image 20250103102212.png]]
$$
\begin{align}
R & :=\{ \{ a,b \},\{ c \},\{ d \},\{ e, f \},\{ g \},\{ h \},\{ j \},\{ i, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \}, \{ e,f \} \}
\end{align}
$$
**Schritt 4**
![[Pasted image 20250103102313.png]]
$$
\begin{align}
R & :=\{ \{ a,b \},\{ c, d \},\{ e, f \},\{ g \},\{ h \},\{ j \},\{ i, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \}, \{ e,f \},\{ c,d \} \}
\end{align}
$$
**Schritt 5**
![[Pasted image 20250103102407.png]]
$$
\begin{align}
R & :=\{ \{ a,b,c, d \},\{ e, f \},\{ g \},\{ h \},\{ j \},\{ i, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \}, \{ e,f \},\{ c,d \}, \{ b,d \} \}
\end{align}
$$
**Schritt 6**
![[Pasted image 20250103102453.png]]
$$
\begin{align}
R & :=\{ \{ a,b,c, d \},\{ e, f \},\{ g \},\{ h \},\{ i, j, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \}, \{ e,f \},\{ c,d \}, \{ b,d \},\{ i,j \} \}
\end{align}
$$
**Schritt 7**
![[Pasted image 20250103102536.png]]
$$
\begin{align}
R & :=\{ \{ a,b,c, d \},\{ e, f \},\{ g, h \},\{ i, j, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \}, \{ e,f \},\{ c,d \}, \{ b,d \},\{ i,j \}, \{ g,h \} \}
\end{align}
$$
**Schritt 8**
![[Pasted image 20250103102628.png]]
$$
\begin{align}
R & :=\{ \{ a,b,c, d, e, f \},\{ g, h \},\{ i, j, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \}, \{ e,f \},\{ c,d \}, \{ b,d \},\{ i,j \}, \{ g,h \}, \{ c,f \} \}
\end{align}
$$


aufspannender Wald:
![[Pasted image 20250103102647.png]]
$$
\begin{align}
R & :=\{ \{ a,b,c, d, e, f \},\{ g, h \},\{ i, j, k \} \} \\
T & := \{ \{ a,b \},\{ i,k \}, \{ e,f \},\{ c,d \}, \{ b,d \},\{ i,j \}, \{ g,h \}, \{ c,f \} \} \\
w(T) & := 1+1+2+2+2+2+3+4=17
\end{align}
$$




