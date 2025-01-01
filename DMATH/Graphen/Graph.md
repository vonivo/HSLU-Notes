---
aliases:
  - Knoten
  - Kante
---
Graphen als mathematische Modelle für netzartige Strukturen in Natur und Technik, z.B. für:
- Strassenentze
- Computernetze
- elektrische Schaltungen
- Programmabläufe
- Wassernetze
- chemische Moleküle
- wirtschaftliche Verfelchtungsnetze
- soziale Netzwerke
- optimale Paare.

Graphen bestehen aus:
- Knoten (Orte im Netz)
- Kanten (Verbindungen von Orten) (siehe [[AD/Algorithmen/Graphen/Graph|AD Graph]])


>[!Definition]
>Ein **ungerichteter** **Graph** $G=(V,E)$ besteht aus:
>1. einer **Knotenemenge** $V=V(G)$ mit der Anzahl Knoten $n:=|V|<\infty$
>2. einer **Kantenmenge** $E=E(G)$ mit der Anzahl Kanten $m:=|E|<\infty$
>wobei jede Kante $e\in E$ zwei (nicht notwendigerweise verschiedene) Knoten aus $V$ zugeordnet sind.
>
>Schreibweise: $e=\{ u,v \}=\{ v,u \}$
>
>Die Knoten $u$ und $v$ heissen dann Endknoten der Kante $e$.
>
>Die Kannte der Form $\{ v,v \}$ heisst **Schlinge (oder Loop)** und zwei verschiedenen Kanten der Form $e=\{ u,v \}$ und $f=\{u,v \}$ heissen **parallel**.
>
>Ein Graph, der weder Schlingen noch parallele Kanten besitzt, heisst **schlichter Graph**.

**Beispiel**
$$
\begin{align}
V&=\{ 1,2,3,4,5 \} \\
E&=\{ \{ 1,2 \},\{ 1,3 \},\{ 1,4 \},\{ 2,3 \},\{,2,4\},\{ 3,4 \},\{ 3,5 \},\{ 4,5 \} \} \\
&=\{ e_{1},e_{2},,e_{3},e_{4},e_{5},e_{6},e_{7},e_{8} \}
\end{align}
$$
![[Pasted image 20250101104029.png]]


