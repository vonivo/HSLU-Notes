>[!info]
>Ein **Graph** ist eine **abstrakte Struktur**, die eine Menge von Objekten zusammen mit den zwischen diesen Objekten bestehenden Verbindungen repräsentiert. Die mathematischen Abstraktionen der Objekte werden **Knoten** genannt. Die **paarweisen Verbindungen** zwischen Knoten heissen **Kanten**.

**Beispiel**
Ein graph aus dem Projektmanagement und dem kritischen Pfad.
![[ProjektmanagementGraph.png]]

## Anwendung
Graphen finden bei sehr vielen Problemen Anwendung:
- Begriffe und Beziehungen (semantisches Netz)
- Computer und Netzwerkverbindungen (Netzwerkplan)
- Elekronische Komponenten und Verbindungen (Routing)
- Flughäfen und Direktflüge (Flugplan)
- Neuronale Netze
- Ortschaften und direkte Strassenverbindungen
- Personen und Abstammung
- Städgte und direkte Bahnverbindungen
- etc.
## Formale Beschreibung
**2-Tupel**
$G = (V,E)$

$V$ -> Knotenmenge (Vertex)
$V=\{ a,b,c,d,e \}$
$E$ -> Kantenmenge (Edge), $E \subseteq V x V$
$E=\{ (a,b), (b,a), (b,c), (a,c), (c,c),(c,d), (a,d) \}, |E| = 7$

**Darstellung**
Knoten $a \in V$ werden als **Kreis**
Kanten $(a,b) \in E$ als **Pfeil** von Konten $a$ zu $b$
![[Graphen2.png]]

## Teilgraph
Ein Teilgraph ist wie der Name sagt ein Teil eines bestehenden Graphen.

**Formale Beschreibung**
$G' = (V', E')$
Knotenmenge $V' \subseteq V$
$V' = \{ a,b,c \}$

Kantenmenge $E' \subseteq E$ und $E' \subseteq V' x V'$
$E' = \{ (a,b),(b,c),(a,c) \}$
![[Teilgraph.png]]
## Gerichteter vs. ungerichteter Graph
Im Allgemeinen sind Graphen **gerichtet**.
Falls **für alle $(x,y) \in E$ auch $(y,x) \in E$ gilt**:
- E ist symmetrisch.
- Bzw. der Graph ist **ungerichtet**.
- Pfeilspitzen können weggelassen werden.
![[UngerichteterGraph.png]]

## Dicht vs. dünn besetzter Graph
### Dicht
Ein Graph dient als dicht besetzt, wenn $|E| \approx |V|^{2}$
![[DichterGraph.png]]

### Dünn
Ein Graph gilt als dünn besiedelt wenn $|E| \ll |V|^{2}$
![[DünnerGraph.png]]

## Pfade
Falls z.B. $(a,b) \in E$, $(b,c) \in E$ und $(c,d) \in E$ existieren, dann existiert ein **Pfad** $(a,b,c,d)$ von $a$ nach $d$ mit der **Länge 3**.
=> Der Knoten $d$ ist von $a$ aus erreichbar.

## Zyklen
Wenn ein Pfad vom Knoten $x$ zu dem Knoten $x$ existiert, ist die ein **Zyklus**.

Ein gerichteter Grpah ist **zyklenfrei** oder **azyklisch** wenn er keine Zyklen enthält.

Ein ungerichteter Graph ist **zyklenfrei** oder **azyklisch**, wenn es zwischen zwei Knoten höchstens 1 Pfad gibt (ohne triviale Zyklen.)
**Triviale Zyklen**
![[TrivialeZyklen.png]]

=> Bei $n$-Knoten und **min. $n$-Kanten** gibt es einen **Zyklus**.

## Bewerteter Graph
**3-Tupel**
$G = (V,E,f(E))$

Die Gewichtsfunktion $f(E)$ ordnet jeder Kante ein Gewicht zu.
Ein Pfad/Weg besitzt:
- eine Länge (Anzahl Kanten)
- eine **bewertete Länge** (Summe aller Gewichte) oder auch Entfernung.

## [[Bäume|Baum]]
Ein Baum ist ein ungerichteter, azyklischer und zusammenhängender Graph.

Ein Baum mit $n$ Knoten besitzt $n-1$ Kanten.

### Spanning Tree
Ein Spanning Tree (Aufgespannter Baum) $G'$ ist ein azyklischer Teilgraph eines ungerichteten, zusammenhängenden Graphen $G$, wobie $G'$ alle Knoten vom $G$ beinhaltet.
![[SpanningTree.png]]

Folgende [[Graphenalgorithmen]] liefern ein Spanningtree:
- [[Breitensuche]]
- [[Tiefensuche]]
- [[Algorithmus von Dijkstra]]