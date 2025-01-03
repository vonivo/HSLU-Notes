>[!Definition]
>Das Gewicht einer Menge $T\subset E$ von Kanten ist die Summe:
>$$
>w(T)=\sum_{\{ u,v \}\in T}w(u,v)
>$$
>Ein **minimal aufspannender [[Baum]] $T$** des gewichteten [[DMATH/Graphen/Graph|Graphen]] $(V,E,w)$ ist ein [[Spannbaum]] $T$ mit der Eigenschaft
>$$
>w(T) \leq w(T')
>$$
>für jeden aufspannenden Baum $T'$ von ($V,E,w$).

![[Pasted image 20250103095458.png]]
## Algorithmus
Sei $a\in V$ ein Knoten eines **gewichteten zusammenhängenden** Graphen $G=(V,E,w)$. Der Algorithmus von Prim berechnet einen minimalen aufspannenden Baum $T$ von $G$ mittels eines Greedy-Algorithmus.

### Initialisierung
$$
\begin{align}
S & :=a \\
T & :=\emptyset
\end{align}
$$
### Ablauf
1. Wähle eine Kante $\{ x,y \}\in E$ minimalen Gewichts mit $x\in S$ und $y \in V\text{\\}S$ ($V$ ohne $S$)
2. Füge der Menge $S$ den Knoten $y$ hinzu.
3. Füge der Menge $T$ die Kante $\{ x,y \}$ hinzu.
4. Wiederhole bis $V\text{\\}S =\emptyset$

**Schritt 1**
![[Pasted image 20250103095911.png]]
$$
\begin{align}
S & :=\{ a,b \} \\
T & := \{ \{ a,b \} \}
\end{align}
$$
**Schritt 2**
![[Pasted image 20250103100205.png]]
$$
\begin{align}
S & :=\{ a,b,d \} \\
T & := \{ \{ a,b \}, \{ b,d \} \}
\end{align}
$$
**Schritt 3**
![[Pasted image 20250103100307.png]]
$$
\begin{align}
S & :=\{ a,b,d,g \} \\
T & := \{ \{ a,b \}, \{ b,d \}, \{ a,g \} \}
\end{align}
$$
**Schritt 4**
![[Pasted image 20250103100508.png]]
$$
\begin{align}
S & :=\{ a,b,d,g,c \} \\
T & := \{ \{ a,b \}, \{ b,d \}, \{ a,g \},\{ d,c \} \}
\end{align}
$$
**Schritt 5**
![[Pasted image 20250103100553.png]]
$$
\begin{align}
S & :=\{ a,b,d,g,c,h \} \\
T & := \{ \{ a,b \}, \{ b,d \}, \{ a,g \},\{ d,c \},\{ g,h \} \}
\end{align}
$$
**Schritt 6**
![[Pasted image 20250103100651.png]]
$$
\begin{align}
S & :=\{ a,b,d,g,c,h,f \} \\
T & := \{ \{ a,b \}, \{ b,d \}, \{ a,g \},\{ d,c \},\{ g,h \},\{ c,f \} \}
\end{align}
$$
**Schritt 7**
![[Pasted image 20250103100728.png]]

$$
\begin{align}
S & :=\{ a,b,d,g,c,h,f,e \} \\
T & := \{ \{ a,b \}, \{ b,d \}, \{ a,g \},\{ d,c \},\{ g,h \},\{ c,f \},\{ f,e \} \}
\end{align}
$$

Spannbaum:
$T=\{\{ a,b \},\{ b,d \},\{a,g  \},\{d,c  \},\{ g,h \},\{c,f \},\{ f,e \}  \}$

![[Pasted image 20250103100747.png]]
