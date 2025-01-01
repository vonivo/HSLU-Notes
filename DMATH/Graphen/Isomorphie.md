>[!Definition]
>Zwei [[DMATH/Graphen/Graph|Graphen]] $G=(V,E)$ umd $G'=(V',E')$ heissen **isomorph**, wenn es eine [[Bijektive Funktionen|Bijektion]] $f:V\to V'$ gibt, welche die Kanten erhält, d.h.
>$$
>e=\{ u,v \}\in E \Leftrightarrow e'=\{ f(u), f(v) \}\in E' 
>$$
>Es gibt also eine bijektive Abbildung, welche die **Nachbarschaftsbeziehungen** beibehält: sind als zwei Knoten $u$ und $v$ in $G$ durch eine Kanten $e\in E$ verbunden, dann sind auch die Bilder dieser Knoten $f(u)$ und $f(v)$ in $G'$ durch eine Kante $e'\in E'$ verbunden. Existiert eine solche bijektive Abbildung, nennt man sie **Isomorphismus** zwischen den Graphen $G$ und $G'$.

Bei einem Isomorphismus muss folgendes immer übereinstimmen:
- Anzahl Knoten
- Anzahl Kanten
- [[Gradliste]]

Ein Graphisomorphismus ist eine [[Einwegfunktion]]. Es ist nämlich einfach, zu einem gegebenen Graphen $G$ einen isomorphen Graphen $G ′$ zu konstruieren: man muss ja nur die Knotenmenge von $G$ [[Permutationen|permutieren]]! Umgekehrt ist es sehr schwer, zu zwei gegebenen isomorphen Graphen $G$ und $G ′$ einen Isomorphismus zu bestimmen: dazu muss man alle möglichen [[Permutationen]] der Knotenmenge durchprobieren, was mit der [[Wachstum von Funktionen|Komplexität]] $O(n!)$ verbunden ist. Ob das Graphen-Isomorphismus-Problem in $P$ ist, oder ob es $NP$-vollständig ist, ist eines der
grossen offenen Probleme der Informatik

**Beispiel 1**
![[Pasted image 20250101105738.png]]
Der Graph rechts ist ein Isomorphismus des Grafens links (nur die Nummerierung wurde vertauscht.)

Die Funktion $f(u)$ lautet so
$$
\begin{array}{c|ccccc}
u & 1 & 2 & 3 & 4 & 5 \\
	\hline f(u) & 3 & 2 & 1 & 4 & 5
\end{array}
$$

=> In diesem Graph ist von Auge erkennbar, dass die Nachbarschaftsbeziehungen eingehalten wurden.

**Beispiel 2**
![[Pasted image 20250101110018.png]]
$$
\begin{array}{c|cccc}
u & 1 & 2 & 3 & 4 \\
\hline f(u) & C & D & A & B
\end{array}
$$
$$
\begin{align}
e&=\{ 1,2 \}\to \{ f(1), f(2) \}=\{ C,D \}\stackrel{?}{\in} E' \implies \checkmark \\
e&=\{ 1,4 \}\to \{ f(1), f(4) \}=\{ C,B \}\stackrel{?}{\in} E' \implies \checkmark \\
e&=\{ 1,3 \}\to \{ f(1), f(3) \}=\{ C,A \}\stackrel{?}{\in} E' \implies \checkmark \\
\vdots \\
e&=\{ 3,4 \}\to \{ f(3), f(4) \}=\{ A,B \}\stackrel{?}{\in} E' \implies \checkmark
\end{align}
$$


## Schere Stein Papier
Alice und Bob legen sich auf drei **nicht isomorphe** (grosse) Graphen $G_{Papier}$, $G_{Schere}$ und $G_{Stein}$ fest.

Dabei soll es nicht (ohne grosse Rechnung) möglich sein, die drei Graphen zu unterscheiden, d.h. sie sollten mindestens gleiche Anzahl Knoten und Kanten, sowie die selbe [[Gradliste]] haben.

- Alice wählt einen zufälligen Isomorphismus des gewählten Graphen aus (z.B. $G_{Stein}'$) und schickt diesen an Bob.
- Bob erkennt nicht welchen Graphen Alice gewählt hat. Nun Wählt Bob eine Graphen aus und sendet diesen Alice.
- Nun Schickt Alice ihre Wahl $G'_{Stein}$ und den verwendenden Isomorphismus ($f(u)$) an Bob und beide können überprüfen, wer gewonnen hat.