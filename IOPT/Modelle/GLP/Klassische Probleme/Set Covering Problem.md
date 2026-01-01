Das Set Covering Problem ist ein Problem der [[Ganzzahlig Lineare Programmierung]].

Gegeben:
- Grundmenge $E$ von $n$ Elementen
- Eine Familie $F$ von $m$ Untermengen der Grundmenge $E$
- Für jedes Element $e\in E$ seien in $F_{e}\subseteq F$ jene Untermengen $S$, welche $e$ enthalten, d.h. $e\in S$.
- Jede Untermenge $S\in F$ hat Kosten $c_{S}$
![[SetCovering.png]]
**Problem**
Wähle eine Untermenge der Familie F mit minimalen totalen Kosten, so dass jedes Element in mindestens einer gewählten Menge enthalten ist.

1. Für jede Untermenge $S\in F$ wird eine [[Binäre Varialben|binäre Variable]] eingeführt. $x_{s}$: 1 Falls die Untermenge $S\in F$ gewählt wird, $0$ sonst.

## Modell
$$
\begin{align}
\text{min} & \sum_{S\in F}c_{S}x_{S} \\
\text{unter den Bedingungen:} \\
 & \sum_{S\in F_{e}}x_{S} \geq 1 & \text{für alle }e \in E \\
 & x \in \{ 0,1 \}
\end{align}
$$