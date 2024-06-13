Ein endlicher Automat ist ein [[Automaten|Automat]] mit einer endlichen Anzahl an Zuständen.

Im Vergleich zu den normalen [[Automaten]]:
**Zustände Z**
- **endliche** Anzahl
- expliziter Startzustand,
- **explizite** Endzustände,
**Eingaben**
- **endliches** Eingabealphabet
**Typen**
- deterministier endlicher Automat (DEA)
- nichtdeterministischer endlicher Automat (NEA)


## Eigenschaften
- Jeder DEA ist definitionsgemäß auch ein NEA. Man kann umgekehrt zeigen, dass jeder NEA (auch $\epsilon$-NEA) in einen DEA überfürht werden kann.
- DEA's sind:
	- einfacher und effiziernter zu programmieren.
	- erfordern für das Lösen des Wortproblems kein Backtracking.
- NEA's sind:
	- leicht zu konstruieren.
	- benötigen weniger Zustände.


## Deterministischer endlicher Automat
### Formale Definition als 5-Tupel
- $Z$: endliche Menge an Zuständen
- $A$: endliche Menge von Symbolen (Alphabet)
- $\delta$: Zustandsübergangsfunktion $\delta: Z x A \to Z$
- $E$: Menge der Endzustände $E \subseteq Z$
- $z_{0}$: Startzustand $z_{0} \in Z$
=> Deterministisch bedeutet, dass der **Folgezustand eindeutig** ist.

### Beispiel [[Typ 3|reguläre Sprache]]
Die Sprache besteht aus folgenden Wörter $L(G_{4}) = \{\text{ha!}, \text{haha!}, \text{hahaha!},\dots\}$.

Definition mit [[Formale Grammatik|formaler Grammatik]]
$N=\{s,X,Y\}$
$T=\{a,h,!\}$
$P=\{s\to hX,X \to aY,Y\to!,Y\to hX \}$
$s$

Definition mit einem [[Regulärer Ausdruck|regulären Ausdruck]]
ha(ha)\*!

#### DEA
$Z= \{z_{0},z_{1},z_{2},z_{3}\}$
$A = \{a,h,!\}$
$\delta = (z_{0}, h) \to z_{1}, (z_{1},a)\to z_{2}, (z_{3},h)\to z_{1}, (z_{2},!)\to z_{3}$
$E= \{z_{3}\}$
$z_{0}$

=> Theoretisch müssen die Zustandsübergänge für jede erdenkliche Kombination von $A$ und $Z$ gemacht werden, praktisch wird dies jedoch nicht nur für die Gültigen Transitions gemacht.
**Als Graph**
![[DEA_graph.png]]
**Als Tabelle**
![[DEA_table.png]]


## Nichtdeterministischer endlicher Automat
### Forale definition als 5-Tuper
- $Z$: endliche Menge an Zuständen
- $A$: endliche Menge von Symbolen (Alphabet)
- $\delta$: Zustandsübergangsfunktion $\delta: Z x A \to \color{red} P(Z)$
- $E$: Menge der Endzustände $E \subseteq Z$
- $z_{0}$: Startzustand $z_{0} \in Z$

=> Nichtdeterministisch bedeutet, dass **mehrere Folgezustände** möglich sind. $P(z)$ steht dabei für die Potenzmenge (Mengen aller Teilmengen).

#### Beispiel Potenzmenge
Menge: $A=\{a,b,c\}$
Leere Menge: $\emptyset$
Mächtigkeit $|A| = 3$
Potenzmenge:
- $P(A) = \{ X|X \subseteq A \}$
- $P(A) = \{ \emptyset, \{ a \}, \{ b \}, \{ c \}, \{ a,b \}, \{ a,c \}, \{ b,c \},\{ a,b,c \} \}$
- $|P(A)| = 2^{|A|} = 2^{3}=8$

### Beispiel reguläre Sprache
Die Sprache besteht aus folgenden Wörter $L(G_{5}) = \{01,000101001001, 1101\}$. Also immer mit der Endung $01$.

Definition mit [[Formale Grammatik|formaler Grammatik]]
$N=\{s,X\}$
$T=\{0,1\}$
$P=\{s\to 0s,s\to1s, s\to_{0}X,X\to!\}$
$s$


Definition mit einem [[Regulärer Ausdruck|regulären Ausdruck]]
(0|1)\*01

### NEA
$Z =\{ z_{0},z_{1},z_{2} \}$
$A =\{ 0,1 \}$
$\delta = (z_{0},0) \to \{ z_{0},z_{1}\},(z_{0},1 \to z_{0},z_{1}\to z_{2})$
$E = \{ z_{2} \}$
$z_{0}$
![[NEA.png]]

### $\epsilon$-NEA
- $Z$: endliche Menge an Zuständen
- $A$: endliche Menge von Symbolen (Alphabet)
- $\delta$: Zustandsübergangsfunktion $\delta: Z x A \to \color{red} P(Z)$
- $E$: Menge der Endzustände $E \subseteq Z$
- $z_{0}$: Startzustand $z_{0} \in Z$

=> Mit $\epsilon$ kann der Automat spontan in einen anderen Zustand wechsel. $\epsilon$ ist kein Symbol bzw $\epsilon \notin A$
![[ENEA.png]]



## NEA in DEA überführen
Um einen NEA in einen DEA zu überführen wird ein Tabelle erstellt die Farblich gekennzeichnet wird, anhand dieser Tabelle lässt sich der DEA erstellen.
![[NEA.png]]

| P(Z)                            | $0 \in A$                      | $1 \in A$                       |
| ------------------------------- | ------------------------------ | ------------------------------- |
| ->$\color{green}z_{0}$          | $\color{red}\{z_{0},z_{1}  \}$ | $\color{green}\{z_{0}\}$        |
| $\color{red}\{z_{0},z_{1}  \}$  | $\color{red}\{z_{0},z_{1}  \}$ | $\color{blue}\{z_{0},z_{2}  \}$ |
| $\color{blue}\{z_{0},z_{2}  \}$ | $\color{red}\{z_{0},z_{2}  \}$ | $\color{green}\{z_{0}\}$        |
| $\emptyset$                     | $\emptyset$                    | $\emptyset$                     |
| $\{ z_{1} \}$                   | $\emptyset$                    | $\{ z_{2} \}$                   |
| $\{ z_{2} \}$                   | $\emptyset$                    | $\emptyset$                     |
| $\{ z_{1},z_{2} \}$             | $\emptyset$                    | $\{ z_{2} \}$                   |
| $\{ z_{0},z_{1},z_{2} \}$       | $\color{red}\{z_{0},z_{2}  \}$ | $\color{blue}\{z_{0},z_{2}  \}$ |
![[NEA2DEA.png]]

## Darstellung [[Formale Sprache]]
Mit einem endlichen Automaten kann eine [[Formale Sprache|formale Sprache]] des [[Typ 3]] dargestellt werden.

- Auf dem Weg von Start zu Ende werden die Wörter erzeugt.
- Findet ein vorgegebenes Wort einen Weg von Start zu Ende gehört es zu der Sprache
![[EndlicherAutomat.png]]