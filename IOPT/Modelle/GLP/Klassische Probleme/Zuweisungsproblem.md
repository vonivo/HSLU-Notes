Gegeben:
- Eine Menge $T$ von $n$ Aufgaben
- Eine Menge $E$ von $n$ Mitarbeitern
- Gewinne $w_{t,e}$ falls Aufgabe $t\in T$ Mitarbeiter $e\in E$ zugewiesen wird.

Jeder Mitarbeiter darf höchstens eine Aufgabe zugewiesen bekommen.
Jeder Aufgabe darf höchsten ein Mitarbeiter zugewiesen werden.

**Problem**
Finde eine zulässige Zuweisung mit maximalem Gewinn

### Modell
$$
\begin{align}
\text{max} & \sum_{t\in T}\sum_{e\in E}w_{t,e}x_{t,e} \\
\text{u. d. B:} \\
 & \sum_{e\in E}x_{t,e} \leq 1 & \text{für alle }t\in T \\
 & \sum_{t\in T}x_{t,e} \leq 1 & \text{für alle }e\in E
\end{align}
$$
