Ein Ganzzahliges lineares Programm ist $GLP = LP + \text{disjunktive Logik}$. Dadurch wird das Modellieren von:
- **Ja/Nein** Entscheidungen
- **Unteilbarkeit** von physischen Entitäten
- **Logische und Falls-Dann** Ausdrücke
- **Fixkosten** und andere **nicht lineare Funktionen**
ermöglicht.

## Binäre Wahl
Verwende einfach **[[Binäre Varialben|binäre Variablen]] um Ja-Nein Entscheidungen** zu modellieren.

**Beispiel: Knapsack Problem**
Gegeben:
- Eine **endliche** Menge $I$ von $n$ Elementen.
- Jedes Element $i\in I$ hat einen Wert $c_{i}$ und ein Gewicht $w_{i}$
- Ein Rucksack hat die Kapazität $K$.

**Problem**
Wähle eine Menge von Elementen mit maximalem Wert unter Einhaltung der Kapazität $K$.

**GLP Modell**
- Für jedes Element $i\in I$ eine binäre Entscheidungsvariable $x_{i}$ mit dem Wert $1$ falls das Element $i$ gewählt wird und $0$ sonst.

$$
\begin{align}
\text{max} & \sum_{i \in I} c_{i}*x_{i} \\
\text{unter den Bedingungen} \\
& \sum_{i\in I} x_{i}w_{i} \leq K \\
 & x\in \{ 0,1 \}
\end{align}
$$

## Abhängige Wahl
Erzwingt, dass eine Aktion $a$ nur durchgeführt werden kann, wenn eine andere Aktion $b$ gemacht wird.

1. Führe zwei binäre Variablen $x_{a}$ und $x_{b}$ ein. (1 falls Aktion gemacht wird, 0 sonst)
2. Bedingung $x_{a} \leq x_{b}$ sagt dann genau dass Aktion $a$ nur gemacht werden kann, wenn Aktion $b$ ausgeführt wird.

| $x_{a}$ | $x_{b}$ | $x_{a}\leq x_{b}$ |
| ------- | ------- | ----------------- |
| 0       | 0       | 1                 |
| 0       | 1       | 1                 |
| 1       | 0       | 0                 |
| 1       | 1       | 1                 |
