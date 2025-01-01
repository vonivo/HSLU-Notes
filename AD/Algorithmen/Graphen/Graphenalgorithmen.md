Ein Graphenalgorithmus ist ein [[Algorithmus]] der sich mit [[AD/Algorithmen/Graphen/Graph|Graphen]] beschäftigt.

Viele Graphenalgorithmen bedingen, dass man all Knoten eins Graphen traversiert / besucht, und zwar gemäss dem Zusammenhalt des Graphen.

Bei Graphen mit [[AD/Algorithmen/Graphen/Graph#Zyklen|Zyklen]] ist zu beachten, dass man nicht in eine Endlosschlaufe gerät. Daher werden Knoten oft markiert:
- WHITE -> noch nicht gefunden
- GRAY -> gefunden
- BLACK -> verarbeitet.

**Man unterscheidet folgende Strategien beim Traversieren:**
- [[Breitensuche]]
- [[Tiefensuche]]

**Algorithmen um alle Pfade zu finden:**
- [[Algorithmus von S. Warshall]]

**Kürzeste Entfernung in einem Graph:**
Von Knoten $x$ zu Knoten $y$ können verschieden Pfade existieren wobei die Pfade:
- Unterschieliche Länge
- Unterschiedliche Entfernung (mit [[AD/Algorithmen/Graphen/Graph#Bewerteter Graph|bewertung]]) (bewertete Länge)
haben.

Das Minimum der bewerteten Länge ist der kürzeste Pfad.

Algorithmen:
- [[Algorithmus von R. Floyd]]
- [[Algorithmus von Dijkstra]]

