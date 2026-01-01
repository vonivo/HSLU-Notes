Gegeben folgendes generelles GLP:
$$
\begin{align}
\text{max } & c^{T}\vec{x} \\
\text{u.d.B:} \\
 & A\vec{x}=b \\
 & x\in \mathbb{Z}^{n}_{+}
\end{align}
$$
(Vereinfachte Schreibweise: Einige Variablen dürfen natürlich kontinuierlich sein und es darf <= und >= Ungleichungen geben)


**Der Lösungsraum** des GLP sei $S=\{ x\in\mathbb{Z}^{n}_{+}|Ax=b \}$

## Beispiel
$$
\begin{align}
\text{max } & 6x-y \\
\text{u.d.B:} \\
 & 8x-2y\leq 15 \\
 & 4x+5y\leq 36 \\
 & x,y \in \mathbb{N}_{+}
\end{align}
$$


![[GLP_Solver.png]]

Um das Problem nun zu lösen, wird der Lösungsraum $S$ sukzessive aufgeteilt:

>[!Definition]
>Aufteilung von $S$ in weitere Untermengen $S_{k}, k \in K$ von $S$ sodass $\cup_{k\in K}S_{k}=S$

Dann gilt:
$$
\begin{align}
z=\text{max}_{k\in K} z_{k} \\
\text{where } \\
z_{k} =\text{max}_{x \in S_{k}}c^{T}x
\end{align}
$$

Die Untermenge $S_{k}$ werden dynamisch kreiert durch die **Branching-Regeln**
Zum Beispiel:
- Falls $x_{i}$ [[Binäre Varialben]] benutzt, $x_{i}=0$ resp. $x_{i}=1$ für die Aufteilung von $S$ in zwei nicht-überschneidende Untermengen:
	- $S_{0}=\{ x\in\mathbb{Z}^{n}_{+}|Ax=b,x_{i}=0 \}$
	- $S_{1}=\{ x\in\mathbb{Z}^{n}_{+}|Ax=b,x_{i}=1 \}$

Die Untermengen werden durch ein impliziter Enumerationsalgorithmus rekursiv gebildet. Daraus entsteht ein Lösungsbaum:
![[Lösungsbaum.png]]


In unserem Beispiel:
![[GLP_Solver2.png]]

Jeder implizite Enumerationsalgorithmus versucht durch ‘**Bounding Prozeduren**’ (Schranken- / Güteabschätzungen) den **Suchbaum möglichst klein** zu halten

Dafür werden folgende Variablen verwendet:
- $\underline{z_{k}}$: untere Schranke für $z_{k}$ gegeben durch eine zulässige Lösung $x\in S_{k}$
- $\bar{z_{k}}$ obere Schranke für $z_{k}$ in GLP gegeben durch Wert der **linearen Relaxation des Unterproblems** assoziiert mit $S_{k}$ (ist ein LP → gut lösbar)

Gegeben ein Enumerationsbaum mit $|K|$ Knoten, Schranken für das gesamte (ursprüngliche) Problem:
- $\underline{z_{k}} = max_{k\in K} \underline{z_{k}}$ ist eine untere Schranke für $z$ (Zielfunktionswert GLP) – $\underline{z}$ also gegeben durch beste bis jetzt gefundene zulässige Lösung
- $\bar{z_{k}} = max_{k\in K^{L}}z_{k}$ ist eine oberer Schranke für $z$, wobei $K^{L}\subseteq K$ die Blätter (Knoten ohne Kinder) des Baums sind - $\bar{z}$ also definiert durch ‘schlechteste Schranke’ eines Blattes

Schranken $\bar{z}$ und $\underline{z}$ werden nach dem Lösen jedes Unterproblems aktualisiert.
Der Algorithmus stoppt, wenn $\underline{z}=\bar{z}$ -> beste gefundene Lösung ist optimal


**Wann muss ein Lösungsraum weiter aufgeteilt werden?**
Keine Aufteilung falls:
- $S_{k}= \emptyset$ (z.B. indirekt bestimmt durch lineare Relaxation)
- $\underline{z_{k}}=\bar{z}$ Optimallösung für $S_{k}$ gefunden
- $\bar{z_{k}}\leq\underline{z}$ Optimallösung in $S_{k}$ kann nicht besser sein als die beste bis jetzt gefundene Lösung mit Wert 𝑧

=> In diesen Fällen wird entsprechender Knoten im Baum gelöscht

=> Falls keine dieser Konditionen festgestellt wird, $S_{k}$ weiter aufteilen gemäss Aufteilungsdefinition, sagen wir in $q$ Untermengen $S_{k,i}, i\in\{ 1,2,\dots q \}$


Beim Aufteilen von $S_{k}$ wird auf folgendes geachtet:
1. Keine Überschneidungen der aufgeteilten Lösungsmengen, d.h. $R(S_{k,i})\cap R(S_{k,j}) \neq\emptyset$ für alle unterschiedlichen $i,j\in \{ 1,2,\dots,q \}$
2. Optimale (fraktionelle) Lösung im aktuellen Problem nicht in einem Lösungsraum eines Unterproblems, d.h. $\bar{x}_{k}\\not\in \cup^{q}_{i=1}R(S_{k,i})$ wobei $R(S_{k,i})$ die lineare Relaxation des Lösungsraumes $S_{k,i}$ ist und $\bar{x}_{k}$ eine optimale Lösung der linearen Relaxation mit Lösungsraum $R(S_{k})$
>[!Error]
>‘Branchen’ auf einer ganzzahligen Variablen, die in der gegebenen optimalen Lösung der linearen Relaxation einen fraktionellen Wert hat:
>$$
>\begin{align}
S_{k_{1}} &= \{ x\in S_{k}|x_{i}\leq \lfloor \bar{x}^{k}_{i} \rfloor  \} \\
S_{k_{2}} &= \{ x\in S_{k}|x_{i} \geq \lceil \bar{x}^{k}_{i} \rceil \}
\end{align}
>$$
>wobei $x_{i}$ die Variable mit fraktionellem Wert $\bar{x}^{k}_{i}$ in der optimalen Lösung der lineare Relaxation des Knotesn $S_{k}$ ist.
>





## Algorithmus
**Notation**
- $GLP^{k}$: GLP welches zu Knoten $k$ gehört, d.h. $z_{k}=max_{x\in S_{k}}c^{T}x$.
- $R(GLP^{k})$: lineare Relaxation von $GLP^{k}$, d.h. $\bar{z}_{k}=max_{x\in R(S_{k})}c^{T}x$
- $L$: List der aktiven Knoten (noch nicht evaluierte Knoten)
- $x^{*},z^{*}$: aktuell beste Lösungen (incumbent solution) und sein Zielfunktionswert.
- $k$ Knotenzähler ($0$ gehöhrt zu $S_{0}=S$)
- $fahter(k)$: Index des Vorgängerknotes von $k$

 1. Initialisierung
	 $L:=\{ 0 \}, z^{*}:=-\infty, k:=0$
 2. Terminierungstest
	 If $L = \emptyset$ return "$x^{*}$ ist eine optimale Lösung", if $z^{*}> -\infty$ else return GLP unzulässig.
3. Knotenauswahl
	Wähle einen Knoten $l\in L$ und lösche $l$ aus $L$
4. Auswertung
	1. Löse $R(GLP^{l})$ (z.B. mit[[Simplex]])
	2. Falls $R(GLP^{l})$ unbeschränkt (nur möglich mit $l=0$)-> **stopp** return GLP unbeschränkt.
	3. If $R(GLP^{l})$ unzulässig, gehe zu Schritt 2
	4. If $\bar{z}^{l}\leq z^{*}$ gehe zu Schritt 2
	5. if $\bar{x}^{l}$ ganzzahlig, setze $\underline{x}^{l}:=\bar{x}^{l}$; else versuche zulässige Lösung $\underline{x}^{l}\in S_{l}$ zu finden (primal Heuristic)
	6. If $\underline{x}^{l}$ gefunden mit einem Wert $\underline{z}^{l}\geq z^{*}$ aktualisiere die beste Lösung mit $x^{*}:=\underline{x}^{l}; z^{*}:=\underline{z}^{l}; L:=L\backslash\{ q\in L|\bar{x}^{father(q)}\leq z^{*} \}$
	7. if $\bar{z}^{l}\leq z^{*}$ gehe zu Schritt 2.
5. Branching
	1. Wähle einen Index $i$ so dass die assoziierte Variablen $\bar{x}^{l}_{i}$ fraktionell ist.
	2. $S_{k+1}=\{ x\in S_{l}|x_{i}\leq \lfloor \bar{x}^{l}_{i} \rfloor \}$
	3. $S_{k+2}=\{ x\in S_{l}|x_{i}\geq \lceil \bar{x}^{l}_{i} \rceil \}$
	4. Aktualisiere $L :=L\cup \{ k+1,k+2 \}$ und $k:=k+2$
	5. Gehe zu Schritt 2



## Bemerkungen

- Unterschiedliche Branching Regeln
	- Branching mit zwei Nachfolgern: ‘most fractional branching’ / ‘least fractional branching’ / Branching basierend auf Pseudokosten
	- Strong Branching
	- GUB and SOS Branchingregeln
- Unterschiedliche Knotenauswahl-Strategien
	- Breitensuche
	- Tiefensuche
	- Best-First Strategie (Knoten, deren Vorgänger den höchsten Wert in der Relaxation hat)
	- Strategien basierend auf Schätzungen der Verbesserung (Zulässigkeit vs. Verbesserung der oberen Schranke)
- Preprocessing wichtig: ändert Input so ab, dass dieser einfacher / schneller bearbeitet werden kann
- **Primale Heuristiken:** zum frühen Finden von guten Lösungen, z.B. Feasibility Pump und Local Branching
- **Cutting Planes** (Schnittebenen): Im Verlauf werden zulässige Bedingungen hinzugefügt, die aktuelle optimale fraktionelle Lösungen ‘abschneiden’ (insb. im Wurzelknoten wichtig)
![[GLP_Solver3.png]]