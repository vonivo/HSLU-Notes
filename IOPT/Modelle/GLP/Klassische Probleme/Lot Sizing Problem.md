Produktion eines einzelnen Produktes über $n$ Perioden. Wobei die Nachfrage für jede Periode gegeben ist. Pro Periode existieren fixe und variable Kosten. Zusätzlich gibt es die Möglichkeit, Produkte zu lagern.

Gegeben:
Für jede Periode:
- Nachfrage $d_{t}$
- Fixe Produktionskosten $f_{t}$
- Variable Produktionskosten $p_{t}$
- Lagerkosten $h_{t}$ (Pro Einheit am Lager am Ende der Periode)
- Startlagermenge $s_{0}$ (Ende Periode 0 = Start Periode 1)

**Entscheidungsproblem**
Produktionsplan, welcher die Nachfrage abdeckt, mit minimalen Gesamtkosten

**Modell**
1. Einführung von $x_{t}$ mit der Anzahl an Produkten welche in Periode $t$ produziert werden.
2. Einführung von $s_{t}$: Lagermenge am Ende von Periode $t$
3. $y_{t}$: 1, falls in Periode $t$ produziert wird, 0 sonst.

$$
\begin{align}
\text{min} &\sum_{t\in T}(y_{t}f_{t}+p_{t}x_{t}+s_{t}h_{t}) \\
\text{u.d.B} \\
& s_{t-1}+x_{t} =d_{t}+s_{t} &\text{für alle }t\in T \\
& x_{t}\leq My_{t} & \text{für alle }t\in T \\
 & y_{t}\in \{ 0,1 \} & \text{für alle }t\in T \\
 & x_{t},s_{t} \geq 0 & \text{für alle }t\in T 
\end{align}
$$
