**Matching**
- Eine Untermenge von Kanten $S\in E$, sodass jeder Knoten zu höchstens einer Kante aus $S$ ‘gehört’ (als Endknoten)
- Ein perfektes Matching: Matching + jeder Knoten ‘gehört’ genau zu einer Kante aus S

Gegeben:
- Ein ungerichteter Graph $G=(V,E)$ mit Knotemenge $V$ und Kantemenge $E$.
- Evtl. mit Gewichten $w_{e}$ für jede Kante $e\in E$

**Entscheidungsprobleme**
- Finde ein Matching mit maximaler Anzahl Kanten (max. Grösse)
- Finde ein Matching mit maximalem totalen Gewicht
- Finde in perfektes Matching mit maximalem totalen Gewicht

## Modell
1. Für jede Kante $e\in E$ führe eine binäre Variable $x_{e}$ ein: 1, falls Kante $e$ ausgewählt ist und 0 sonst.
2. Für jeden Knoten $i\in V$, sei $E_{i}\subseteq E$ die Untermenge der Kanten, welche Knoten $i$ als Endknoten haben.

Modell mit maximalem Gewicht:
$$
\begin{align}
\text{max} & \sum_{e\in E}w_{e}x_{e} \\
\text{u.d.B:} \\
 & \sum_{e\in E_{i}}x_{e} \leq 1 & \text{für alle }i\in V \\
 & x_{e} \in \{ 0,1 \}
\end{align}
$$
=> mit $w_{e} =1$ für alle $e \in E$ ein Matching mit max. Anzahl Kanten.
=> Für ein perfektes Matching, ersetze $\leq$ mit $=$


