Da der [[Geometrischer Ansatz]] unmöglich mit mehr als 3 Variablen ist, ist ein Algorithmus notwendig.

Aufgrund der Eigenschaften der linearen Optimierung
- müssen nur [[Extremalpunkt|Extremalpunkte]] des Lösungsraums ([[Polyeder]]) betrachtet werden.
- Ein Extrempunkt, der lokal optimal ist, ist global optimal.

## Simplex -> Ansatz
1. Starte aus einem Eckpunkt.
2. Solange ein benachbarter Eckpunkt existiert, der einen besseren Zeilfunktionswert ergibt, gehe zu einem solchen Eckpunkt, sonst **Ende**. Der erreichte Eckpunkt ist **optimal**

Um diesen Ansatz durchzuführen, müssen folgende Fragen beantwortet werden:
1. Wie wird ein Eckpunkt dargestellt?
2. Wie erkennt man, dass der aktuelle Eckpunkt optimal ist?
3. Wie erkennt man, dass es kein endliches Optimum gibt?
4. Was ist ein "Nachbareckpunkt" eines Eckpunkts?
5. Wie gelangt man zu einem besseren benachbarten Eckpunkt effizient?
6. Wie wird ein Starteckpunkt im Allgemeinen gefunden?


## Standardform
Die Standardform eines [[IOPT/Optimierungsproblem|Optimierungsproblem]] sieht wie folgt aus:

Maximiere $\vec{c}x$, $x\in\mathbb{R}^{n}$ unter den Bedingungen:
$$
\begin{align}
Ax &= \vec{b} & A \in \mathbb{R}^{m\times n}\\
x&\geq 0
\end{align}
$$
Es gilt zu Beachten, dass der [[Rang einer Matrix|Rang der Matrix]] $Rg(A) = m$ der Anzahl Zeilen von $A$ entspricht. Dadurch wird sichergestellt, dass keine Gleichung redundant ist.

**Beispiel**
Maximiere $30x_{1}+20x_{2}+15x_{3}$ unter den Bedingungen
$$
\begin{align}
3x_{1}+2x_{2}+x_{3} & \leq 60 \\
6x_{1}+x_{2}+5x_{3} & \leq 120 \\
4x_{1}+x_{2}+5x_{3} & \leq 100 \\
3x_{1}+x_{2}+4x_{3} & \leq 80 \\
x_{1}\geq 0,x_{2}\geq 0,x_{3}&\geq 0
\end{align}
$$
1. Einführen von 4 **Schlupfvariablen** (ein pro Ungleichung ausser ganzzahligkeist Vorderung): $x_{4},x_{5},x_{6},x_{7}$
2. Bedingungen umformen:
$$
\begin{align}
3x_{1}+2x_{2}+x_{3} & +x_{4} &&&& = 60 \\
6x_{1}+x_{2}+5x_{3} & & +x_{5} &&& = 120 \\
4x_{1}+x_{2}+5x_{3} & & & +x_{6} && = 100 \\
3x_{1}+x_{2}+4x_{3} & & & & +x_{7} & = 80 \\
x_{1}\geq 0,x_{2}\geq 0,x_{3}\geq 0,x_{4}\geq &0,x_{5}\geq 0,x_{6}\geq 0x_{7}\geq 0
\end{align}
$$
3. Nun lautet das Problem
Maximiere $30x_{1}+20x_{2}+15x_{3} + (0x_{4}+0x_{5}+0x_{6}+0x_{7})$ unter den Bedingungen
$$
\begin{align}
3x_{1}+2x_{2}+x_{3} & \leq 60 \\
6x_{1}+x_{2}+5x_{3} & \leq 120 \\
4x_{1}+x_{2}+5x_{3} & \leq 100 \\
3x_{1}+x_{2}+4x_{3} & \leq 80 \\
x_{1}\geq 0,x_{2}\geq 0,x_{3}&\geq 0
\end{align}
$$

Daraus kann nun die Standardform hergestellt werden:
$$
\vec{c} = \begin{pmatrix}
30 \\
20 \\
15 \\
0 \\
0 \\
0 \\
0
\end{pmatrix}, \vec{x}=\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4} \\
x_{5} \\
x_{6} \\
x_{7}
\end{pmatrix},
A=\begin{bmatrix}
3 & 2 & 1 & 1 &  &  &  \\
6 & 1 & 5 &  & 1 &  &  \\
4 & 1 & 5 &  &  & 1 &  \\
3 & 1 & 4 &  &  &  & 1
\end{bmatrix},
\vec{b} = \begin{pmatrix}
60 \\
120 \\
100 \\
80
\end{pmatrix}
$$
Also:
Minimiere: $$
\begin{pmatrix}
30 \\
20 \\
15 \\
0 \\
0 \\
0 \\
0
\end{pmatrix}^{T}\times\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4} \\
x_{5} \\
x_{6} \\
x_{7}
\end{pmatrix}
$$
unter den Bedingungen:
$$
\begin{bmatrix}
3 & 2 & 1 & 1 &  &  &  \\
6 & 1 & 5 &  & 1 &  &  \\
4 & 1 & 5 &  &  & 1 &  \\
3 & 1 & 4 &  &  &  & 1
\end{bmatrix}\times\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4} \\
x_{5} \\
x_{6} \\
x_{7}
\end{pmatrix} = \begin{pmatrix}
60 \\
120 \\
100 \\
80
\end{pmatrix}
$$

## Wie wird ein Eckpunkt dargestellt?
Eine Basis einer Matrix $A$ ist eine reguläre $m\times m$ Untermatrix von $A$, d.h. eine Auswahl von $m$ linear unabhängigen Kolonnen von $A$.

**Beispiele**
![[Pasted image 20251230143352.png]]
Gegeben ist nun eine Basis $B$. Jetzt kann das Gleichungssystem $Ax=b$ als $Bx^{B}+Nx^{N}=b$ geschrieben werden. ($N$ ist die Restmatrix, also die 3 verbleibenden Spalten von $A$)

Die Komponenten von $x^{B}$ heissen **Basisvariablen** und beinhalten nur die Ausgewählten Spalten.

**Beispiel**
$$
A=\begin{bmatrix}
3 & 2 & 1 & 1 \\
6 & 1 & 5 &  & 1 \\
4 & 1 & 5 &  &  & 1 \\
3 & 1 & 4 &  &  &  & 1
\end{bmatrix},
B=\begin{bmatrix}
2 \\
1 & 1 \\
1 &  & 1 \\
1 &  &  & 1
\end{bmatrix},
N=\begin{bmatrix}
3 & 1 & 1 \\
6 & 5 \\
4 & 5 \\
3 & 4
\end{bmatrix}
$$
Jetzt haben wir die Splaten $2,5,6,7$ selektiert.
$$
x^{B}=\begin{pmatrix}
x_{2} \\
x_{5} \\
x_{6} \\
x_{7}
\end{pmatrix},
x^{N}=\begin{pmatrix}
x_{1} \\
x_{3} \\
x_{4}
\end{pmatrix}
$$
### Basislösung
Die Basislösung welche zur Basis $B$ gehört ist definiert durch $Bx^{B}=b, x^{N}=0$.
Umwandeln:
$$
\begin{align}
Bx^{B}&=b \\
B^{-1}Bx^{B}&=B^{-1}b \\
Ix^{B}&=B^{-1}b \\
x^{B}&=B^{-1}b
\end{align}
$$
=> **Sehr effizient Lösbar**

Die Basislösung von $B$ heisst **zulässig**, falls $x^{B}=B^{-1}b\geq 0$ (Alle Komponenten von $x^{B}$ nicht negative Werte haben.)
=> $B$ wird eine **zulässige Basis** genannt.

>[!Definition]
>Jeder Eckpunkt entspricht mindestens einer zulässigen Basis, und jede zulässige Basis entspricht genau einem Eckpunkt.


## Wie erkennt man, dass der aktuelle Eckpunkt optimal ist?

Gegeben eine Basis $B$, dann kann das [[IOPT/Optimierungsproblem|Optimierungsproblem]]
$$
\begin{align}
\text{max } &&\vec{c}^{T}\times\vec{x}  \\
\text{u.d.B:}  \\
&&A\times \vec{x}=b \\
&&\vec{x}\geq 0
\end{align}
$$
wie folgt geschrieben werden:
$$
\begin{align}
\text{max } &&c^{B}x^{B}+c^{N}x^{N}  \\
\text{u.d.B:}  \\
&&Bx^{B}+Nx^{N}=b \\
&&x^{B}\geq 0,x^{N}=0
\end{align}
$$
Nun wird nach $x^{B}$ umgeformt:
$$
\begin{align}
Bx^{B}+Nx^{N} & =b \\
x^{B}+B^{-1}Nx^{N} & =B^{-1}b \\
x^{B} & =B^{-1}b-B^{-1}Nx^{N}
\end{align}
$$
Setzt man dies in das Problem ein, erhält man:
$$
\begin{align}
\text{max } &&c^{B}(B^{-1}b-B^{-1}Nx^{N})+c^{N}x^{N}  \\
\text{u.d.B:}  \\
&&x^{B} =B^{-1}b-B^{-1}Nx^{N} \\
&&x^{B}\geq 0,x^{N}=0
\end{align}
$$
Daraus wird die **Tableau Form**:
$$
\begin{align}
\text{max } &&c^{B}B^{-1}b + (c^{N}-c^{B}B^{-1}N)x^{N}  \\
\text{u.d.B:}  \\
&&x^{B} =B^{-1}b-B^{-1}Nx^{N} \\
&&x^{B}\geq 0,x^{N}=0
\end{align}
$$
![[Pasted image 20251230163306.png]]
- $\gamma := c^{N}-c^{B}B^{-1}N$: Vektor der **reduzierten Kosten**
- $\beta := B^{-1}b$: "aktuelle" zulässige Basislösung
- $\alpha := B^{-1}N$

Somit entsteht das Problem
$$
\begin{align}
\text{max } &&c^{B}\beta+\gamma x^{N}  \\
\text{u.d.B:}  \\
&&x^{B} =\beta-\alpha x^{N} \\
&&x^{B}\geq 0,x^{N}=0
\end{align}
$$
>[!Definition]
>Falls $B$ eine zulässige Basis ist, für welche alle reduzierten Kosten nicht positiv sind, i.e., (reduzierter Kostenvektor) $\gamma \leq 0$, dann ist die entsprechende Basislösung optimal.


## Wie erkennt man, dass es kein endliches Optimum gibt?
>[!Definition]
>Falls $B$ eine zulässige Basis ist und es gibt einen Index $j\in\{ 1,\dots,n-m \}$ so dass $\gamma_{j}>0$ und $\alpha_{j}\leq 0$, dann gibt es kein endliches Optimum.

Sprich, falls es einen Index in den reduzierten Kosten gibt, bei welchem die Komponente grösser als 0 ist und bei derselben Spalte in $\alpha$ alle Komponenten kleiner gleich 0 sind, gibt es kein Optimum.

## Was ist ein "Nachbareckpunkt" eines Eckpunkts?
Der Nachbarschaftsbegriff wird nun auf die Basen und nicht auf die Eckpunkte definiert.

**Nachbarschaft**
Sei $B$ ein Basis von $A$ und $A=(B,N)$. Eine Basis $B'$ von $A$ ist eine benachbarte Basis von $B$ falls $B'$ aus $B$ durch Herausnehmen **einer** Kolonne von $B$ und Hineinnehmen **einer** Kolonne von $N$ erhalten wird.

## Wie gelangt man zu einem besseren benachbarten Eckpunkt effizient?
Sei $B$ eine zulässige Basis und $\gamma, \alpha$ und $\beta$ definiert wie vorher.

>[!Definition]
>Um einen **besseren** Nachbar zu finden:
>(i) Wähle eine in $B$ eintretende Kolonne von $N$: Finde einen Index $j, j\in\{ 1,\dots,n-m \}$ mit positiven reduzierten Kosten $\gamma_{j}>0$.
>(ii) Wähle eine aus $B$ austretende Kolonne : Finde einen Index $i, i\in{1,\dots,n}$ so dass $$
\frac{\beta_{i}}{\alpha_{i,j}}=min\left\{  \frac{\beta_{r}}{\alpha_{r,j}}:\alpha_{r,j}>0,1\leq r\leq m  \right\}
$$

# Algorithmus
1. Starte mit einer zulässigen Basis $B = (A_{B(1)},\dots,A_{B(m)}$ und entsprechender Basislösung $x^{B}=\beta:=B^{-1}b,x^{N}=0$ und Zielfunktionswert $z=c^{B}\beta$.
2. Sind alle reduzierten Kosten $\gamma_{j}=c_{N(j)}-c^{B}B^{-1}A_{N(j)}\leq 0$? Falls ja, Basislösung ist optimal -> Stopp. Sonst finde Kolonne $j$ mit $\gamma_{j}>0$ und gehe zu Schritt 3.
3. Die Kolonne $A_{N(j)}$ kommt in die Basis $B$ hinein.
   Find $\alpha_{j}:=B^{-1}A_{N(j)}$. Falls $\alpha_{j}\leq 0$, das Optimum ist nicht begrenzt -> Stopp.
   Sonst finden einen Index $i$ so dass:
$$
\delta:=\frac{\beta_{i}}{\alpha_{i,j}}=min\left\{  \frac{\beta_{r}}{\alpha_{r,j}}:\alpha_{r,j}>0,1\leq r\leq m  \right\}
$$
	Aktualisiere Lösung: $x_{B(r)}:=x_{B(r)}-\delta \alpha_{r,j}, r=1,\dots,m, x_{N(j)}:=\delta$.
	Ersetze Kolonne $A_{B(i)}$ mit $A_{N(j)}$ in $B$ (und $A_{N(j)}$ mit $A_{B(i)}$ in $N$)
4. Gehe zu Schritt 2.