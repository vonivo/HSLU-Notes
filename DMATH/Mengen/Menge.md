>[!Info]
>Eine **Menge** ist eine **ungeordnete Zusammenfassung** wohldefinierter, **unterscheidbarer** Objekte genannt *Elemente* zu einem Ganzen.
>Für irgendein Objekt $x$ gilt dann bezüglich der Menge $A$ entweder $x\in A$ oder $x\notin A$.

## Beispiel
Endliche Mengen lassen sich durch Aufschreiben der in ihnen enthaltenen Elemente beschreiben: $A=\{0,1,2,3,...,100\}$

Oder: $A=\{n\in \mathbb{N} |n<101\}$.

## Gleichheit
>[!Info]
>Zwei Mengen $A$ und $B$ sind **gleich** ($A=B$), falls sie dieselben Elemente enthalten, d.h. wenn $A$ in $B$ enthalten ist und umgekehrt: $(A\subset B)\land(B\subset A)$.

## Spezielle Mengen
## Teilmenge
$A$ ist eine **Teilmenge** von $B$, geschrieben $A\subset B$, wenn $\forall x(x\in A\to x\in B)$. Es gilt auch $A\subset A$.

### Leere Menge
Die leere Menge ist eine Menge ohne Elemente, geschrieben $\emptyset$.
Für jede Menge $A$ gilt $\emptyset \subset A$.

### Kardinalität
Ist $S$ eine endliche Menge, dann bezeichnet $|S|$ die **Kardinalität** (Anzahl aller Elemente) von $S$.

### Potenzmenge
Die **Potenzmenge** $P(S)$ oder $2^{S}$ der Menge $S$ besteht aus der Menge aller Teilmengen $A\subset S$.

**Beispiel**:
$$
\begin{align}
S&=\{ 1,2 \} \\
P(S)=2^{S}&=\{ \emptyset, \{ 1 \},\{ 2 \},\{ 1,2 \} \}
\end{align}
$$
Allgemein gilt: $|2^{S}|=2^{|S|}$.

## Schreibweise mit Bitstring
Jede endliche Menge $A$ und Teilmenge von $A$ kann mit einem Bitstring der Länge $|A|$ dargestetllt werden:
$$
\begin{align}
A=\{ 0,4,6,8,9 \} &=11111 \\
\{ 4 \} \subset A&=01000 \\
\{ 0,6,9 \}\subset A&=10101
\end{align}
$$
Jedes Bit gibt an, ob das Element in der Menge enthalten ist.