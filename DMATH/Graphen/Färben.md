Die Färbung eines Graphen ist, wenn man die Knoten so einfärbt, dass zwei benachbarte Knoten nicht dieselbe Farbe haben.

>[!Definition]
>Unter einer **Färbung** (der Knoten) eines [[DMATH/Graphen/Graph|Graphen]] $G=(V,E)$, versteht man eine Abbildung $c:V\to C$ so, dass $c(u)\neq c(v)$, falls $\{ u,v \}\in E$

- Graphen mit Schlingen lassen sich nicht färben.
- Parallel Kanten beeinflussen die Färbung nicht.
## Algorithmus
Wir färben folgenden Graphen mit den Farben $1-4$:
![[Pasted image 20250102115805.png]]![[Pasted image 20250102115810.png]]
1. Wir färben den ersten Knoten $1$ mit der Tiefsten Farbe.
2. Von da aus gehen wir eine Kante weiter und wählen die **tiefste erlaubte** Farbe um den Graphen zu färben.
3. Wiederhole Schritt 2 bis der Graph vollständig gefärbt ist.
![[Pasted image 20250102120106.png]]
**Anwendung**
Das Färben eines Graphen kann verwendet werden um z.B.
- Frequenzplanung durchzuführen
- Prüffungsplanung usw.
## Chromatische Zahl
Die kleinste Zahl der Farben welche benötigt werden wird **chromatische Zahl** von $G$ genannt. Kurz $\chi(G)$.

Es gilt folgende Abschätzung:
$$
1\leq \chi(G)\leq \Delta(G)+1
$$
$\implies \Delta(G)=$ [[Knotengrad|maximaler Grad]] von $G$.

**Beweis**
Als Farben zählen wird die Zahlen $1,2,3,\dots$

Wir färben die Knoten $v_{1},v_{2},v_{3},\dots$ nacheinander zunächst $v_{1}$ mit der Farbe $1$ usw.

Wenn wir zu irgendeinem Knoten $v_{i}$ kommen, färben wir ihn mit der kleinsten noch erlaubten Farbe.

Wie viele Farben können verboten sein? Schlimmstenfalls
- ist $v_{i}$ ein Knoten mit maximalen Grad $\Delta(G)$
- alle $\Delta(G)$ Nachbarn von$v_{i}$ sind bereits gefärbt und
- alle $\Delta(G)$ Nachbarn von $v_{i}$ sind verschieden gefärbt.

Dann sind $\Delta(G)$ Farben bereits vergeben und wir benötigen eine mehr, also $\Delta(G)+1$

### Einige chromatische Zahlen
$$
\begin{align}
\chi(K_{n}) & =n \\
\chi(C_{2k}+1) & =3 \\
\chi(C_{2k}) & =2
\end{align}
$$
>[!Theorem]
>Ein [[Planare Graphen|planarer Graph]] kann mit **vier** Farben gefärbt werden, d.h. die chromatische Zahl eines ebenen Graphen ist nicht grösser als vier.

