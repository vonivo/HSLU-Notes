Gegeben:
- Menge $V$ von $n$ Knoten
- Für jedes (geordnete) Paar von Knoten $(i,j) \in V\times V$, eine (kürzeste) Distanz von $d_{i,j}$ von $i$ zu $j$
- Terminologie: $(i,j)$ ist ein Bogen (arc), $A=V\times V$ die Bogenmenge

**Problem**
Finde eine Tour, welche alle Knoten besucht und die totale Distanz minimiert.

## Modell
**Entscheidungsvariablen**
Für jeden Bogen $(i,j\in A)$ führe eine [[Binäre Varialben|binäre Variable]] $x_{i,j}$ ein. 1, falls direkt von $i$ nach $j$ gegangen wird, sonst 0

**Bedingungen**
- $x_{i,j} =0$ für alle $i\in V$, kein Loop
- Ausgewählte Bögen (jene mit $x_{i,j}$ = 1) bilden einen Zyklus (eine Tour)

**Zielfunktion**
Minimiere Gesamtlänge
$$
\sum_{(i,j)\in A}d_{i,j}x_{i,j}
$$

**Code**
![[CP_TSP_Code1.png]]

## Bemerkungen
- Lösungszeit evtl. beschränken (generell so möglich)
	- Code: `solver.parameters.max_time_in_seconds = 10.0`
- ‘Reines’ TSP besser lösbar mit anderen Technologien
- Aber CP Modelle flexibler (und z.T. besser) für Probleme in der Praxis
- Gibt auch andere CP Modelle als das besprochene, z.B. mit (Haupt-) Variablen $y_{i}$ : $i$-ter besuche Ort, $i = 1, …, n$
	- Komplexer zum Formulieren (insb. Abbilden der Zielfunktion)
	- Waren in meinen Experimenten nicht besser bezüglich Lösbarkeit
- Google OR-Tools Routing Library
	- Routing-Probleme so wichtig / häufig anzutreffen, dass spezielle API angeboten wird
	- Nur eine Schicht oberhalb des gängigen Constraint Programming APIs
	- Für eines oder mehrere Fahrzeuge
	- Zusätzliche Bedingungen: Fahrzeugkapazitäten, mix aus Abholen (pick-up) und Auslieferung (delivery), einfach modellierbar
	- Aber: Package hat heuristischen Charakter – findet hoffentlich gute Lösungen, aber nie garantiert optimale Lösungen
	- Details, siehe: https://developers.google.com/optimization/routing
![[CP_TSP_Code2.png]]