>[!Definition]
>Sei $G=(V,E)$ ein [[DMATH/Graphen/Graph|Graph]]. Das **chromatische Polynom** $P(G,x)$ gibt für jedes $x\in\mathbb{N}$ die Anzahl der zulässigen [[Färben|Färbungen]] von $G$ mit höchstens $x$ Farben an.

Das chromatische Polynom wird mittels der [[Dekompositionsgleichung]] rekursiv bestimmt.

Es gilt z.B.
$$
\begin{align}
P(G,2) & = \text{Anzahl Färbungen mit 2 Farben} \\
P(G,3) & = \text{Anzahl Färbungen mit 3 Farben} \\
\vdots \\
P(G,n) & = \text{Anzahl Färbungen mit n Farben}
\end{align}
$$
**Beispiel**
Das chromatische Polynom des folgenden Graphen lautet $P(G,x)=x^{2}$
![[Pasted image 20250102122613.png]]
Daraus folgen folgende Färbungen:
![[Pasted image 20250102122650.png]]

## Bestimmen der [[Färben#Chromatische Zahl|chromatischen Zahl]]
>[!Theorem]
>Die chromatische Zahl eins Graphen $G$ kann wie folgt bestimmt werden:
>$$
>\chi(G)=min\{ x\in\mathbb{N}|P(G,x)>0 \}
>$$


## Bekannte chromatische Polynome
>[!Theorem]
>Sie $G$ der Graph mit $n$ Knoten und der leeren Kantenmenge $E=\emptyset$. Dann gilt $P(G,x)=x^{n}$

**Beweis**: Sind $x$ Farben, so kann der erste Knoten alle $x$ Farben haben, der zweite wieder alle $x$ Farben und so weiter bis zu Knoten $n$ welcher auch wieder alle $n$ Farben haben kann.

>[!Theorem]
>Sei $K_{n}$ der vollständige Graph mit $n$ Knoten. Dann gilt $P(K_{n},x)=x(x-1)\dots (X-n+1)$.

**Beweis**: Sind $x$ Farben geben, dann kann der erste Knoten mit $x$ Farben tragen, Da alle Knoten miteinander verbunden sind, kann der zweiten Knoten kann noch $x-1$ Farben Tragen, der dritte noch $x-2$ usw.

>[!Theorem]
>Sei $T_{n}$ ein Baum mit $n$ Knoten. Dann gilt $P(T_{n},x)=x\cdot (x-1)^{n-1}$

**Beweis**: Sind $x$ Farben gegeben, dann kann der Wurzelknoten $x$ Farben tragen, alle Kindknoten können dann wieder $x-1$ Farben tragen, dasselbe gilt wiederum für deren Kinder.

>[!Theorem]
>Das chromatische Polynom $P(C_{n},x)$ eines Kreises $C_{n}$ mit $n\geq 1$ Knoten ist gegebend durch:
>$$
>P(C_{n},x)=(x-1)^{n}+(-1)^{n}(x-1)
>$$

