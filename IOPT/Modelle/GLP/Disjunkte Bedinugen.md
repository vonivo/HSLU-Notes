Wenn eine Wahl besteht, welche Bedingung erfüllt werden soll, kann folgendes Verfahren genutzt werden. Dabei wird zwischen Bedingungen $a$ oder Bedingung $b$ entschieden.

**Beispiel**
Die Formel $\sum_{i=1}^{n}a_{i}x_{i}\geq b$ OR $\sum_{i=1}^{n}c_{i}x_{i}\geq d$ muss erfüllt werden.

Diese Bedingungen kann wie folgt linearisiert werden:
1. Definiere eine [[Binäre Varialben|binäre Variable]] $y$: 1, falls erste Bedingung erfüllt werden muss oder 0, falls die zweite Bedingung erfüllt werden muss.
2. Modelliere die Bedingungen so:
$$
\begin{align}
\sum_{i=1}^{n}a_{i}x_{i}&\geq b-(1-y)M \\
\sum_{i=1}^{n}c_{i}x_{i}&\geq d-yM
\end{align}
$$
3. Wähle $M$ genügend gross, um die Bedingungen aufzuheben. $M$ sollte aber so tief wie möglich gewählt werden.

**Wahl von $M$**
$$
\begin{align}
M & \geq b-\sum_{i}^{n}a_{i}x_{i} \\
M & \geq d-\sum_{i=1}^{n}c_{i}x_{i}
\end{align}
$$


## Scheduling Beispiel
Zwei Aktivitäten $i$ und $j$ brauchen die gleiche Maschine für ihre Bearbeitung während $p_{i}$ resp. $p_{j}$ Zeiteinheiten.

Die Maschine kann nur einen Auftrag gleichzeitig durchführen -> keine parallele Verarbeitung.

Entweder $i$ vo $j$ oder umgekehrt.

1. Führe Variablen $x_{i}$ und $x_{j}$ ein: Startzeit der Bearbeitung von $i$ resp. $j$.
2. Nun soll $x_{i}-x_{j}\geq p_{j}$ ODER $x_{j}-x_{i}\geq p_{i}$ gelten.
3. Führe $y$ ein. 1, falls $i$ vor $j$ gestartet wrid und 0 sonst.

**Bedingungen**
$$
\begin{align}
x_{i}-x_{j}&\geq p_{j}-yM \\
x_{j}-x_{i} & \geq p_{i}-(1-y)M \\
y\in &\{ 0,1 \}
\end{align}
$$

## Probleme mit Fixkosten
In vielen Problemstellungen fixe Kosten und variable Kosten mit einer Entscheidung assoziiert. 

Gegeben:
- Ein gerichteter [[DMATH/Graphen/Graph|Graph]] $G=(V,A)$ mit Knotenmenbe $V$ und Bogenmenge $A$.
- Fixkosten $c_{i,j}\geq 0$ falls Bogen $(i,j)\in A$ *geöffnet* wird.
- Variable Kosten $d_{i,j}\geq 0$ für jede Einheit, welche über Bogen $(i,j)\in A$ gesendet wird.
- Nettoflussmenge $b_{i}$ für jeden Konten $i\in V$

**Problem**
Finde einen zulässigen Fluss minimaler Gesamtkosten.

1. Eine nicht-negative kontinuierliche Variable $x_{i,j}$ für jeden Bogen $(i,j)\in A$ wie viel das Versandt wird.

### Modell ohne Fixkosten
$$
\begin{align}
\text{min} & \sum_{(i,j)\in A}d_{i,j}x_{i,j} \\
\text{ unter den Bedingungen} \\
 & \sum_{j\in V|(i,j)\in A}x_{j,i} - \sum_{j\in V|(i,j)\in A}x_{i,j} = b_{i} & \text{für alle }i\in V
\end{align}
$$
### Modell mit Fixkosten
- führe $y_{i,j}$ ein. 1, falls der Bogen geöffnet wird, sonst 0
$$
\begin{align}
\text{min} & \sum_{(i,j)\in A}d_{i,j}x_{i,j} + \sum_{(i,j)\in A}c_{i,j}y_{i,j} \\
\text{ unter den Bedingungen} \\
 & \sum_{j\in V|(i,j)\in A}x_{j,i} - \sum_{j\in V|(i,j)\in A}x_{i,j} = b_{i} & \text{für alle }i\in V \\
 & x_{i,j} \leq My_{i,j} & \text{für alle }(i,j) \in A
\end{align}
$$

