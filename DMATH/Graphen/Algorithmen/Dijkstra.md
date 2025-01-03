Der Algorithmus von Dijkstra (1959, Edsger Wybe Dijkstra, 11. Mai 1930 bis 6. Aug. 2002, Turing Award 1972) berechnet den Abstand
$$
L(u):=d(a,u)
$$
von $a$ zu jedem Knoten $u\in V$.

Er liefert außerdem für jeden [[DMATH/Graphen/Graph|Knoten]] $u\in V-\{ a \}$ den Vorgänger $p(u)=u_{n-1}$ von $u$ in einem kürzesten Weg.
$a=u_{0},u_{1},\dots,u_{n-1},u_{n}=u$
von $a$ nach $u$.

## Initialisierung
$$
\begin{align}
S & :=0 \\
L(a) & :=0 &  \\
L(u) & := \infty
\end{align}
$$
## Ablauf
1. Wähle eine Knoten $s\in V-S$ mit minimalem $L(s)$
2. Falls $L(s)=\infty$, dann HALT.
3. Füge den Knoten $s$ der [[Menge]] $S$ hinzu.
4. Falls $S=V$, dann HALT.
5. Für jeden Nachbarn $y\in V-S$ des Knoten $s$:
   Falls $L(y)>L(s)+w(s,y)$, ersetze $L(y)$ durch $L(s)+w(s,y)$ (und $p(y)$ durch $s$) anderfalls tue nichts und gehe zu Schritt 1.

**Initialisierung
![[Pasted image 20250103093145.png]]

| $L(a)$           | $0$      |     |     |     |     |     |     |
| ---------------- | -------- | --- | --- | --- | --- | --- | --- |
| $L(b)$<br>$p(b)$ | $\infty$ |     |     |     |     |     |     |
| $L(c)$<br>$p(c)$ | $\infty$ |     |     |     |     |     |     |
| $L(d)$<br>$p(d)$ | $\infty$ |     |     |     |     |     |     |
| $L(e)$<br>$p(e)$ | $\infty$ |     |     |     |     |     |     |
| $L(f)$<br>$p(f)$ | $\infty$ |     |     |     |     |     |     |
| $L(g)$<br>$p(g)$ | $\infty$ |     |     |     |     |     |     |
| $S$              |          |     |     |     |     |     |     |
**Schritt 1**
![[Pasted image 20250103093514.png]]

| $L(a)$           | $0$             |                          |     |     |     |     |     |
| ---------------- | --------------- | ------------------------ | --- | --- | --- | --- | --- |
| $L(b)$<br>$p(b)$ | $\infty$        | $\color{yellow}1$<br>$a$ |     |     |     |     |     |
| $L(c)$<br>$p(c)$ | $\infty$        | $\color{yellow}2$<br>$a$ |     |     |     |     |     |
| $L(d)$<br>$p(d)$ | $\infty$        | $\color{yellow}2$<br>$a$ |     |     |     |     |     |
| $L(e)$<br>$p(e)$ | $\infty$        |                          |     |     |     |     |     |
| $L(f)$<br>$p(f)$ | $\infty$        |                          |     |     |     |     |     |
| $L(g)$<br>$p(g)$ | $\infty$        |                          |     |     |     |     |     |
| $S$              | $\color{blue}a$ |                          |     |     |     |     |     |
**Schritt 2
![[Pasted image 20250103093937.png]]

| $L(a)$           | $0$             |                   |                          |     |     |     |     |
| ---------------- | --------------- | ----------------- | ------------------------ | --- | --- | --- | --- |
| $L(b)$<br>$p(b)$ | $\infty$        | $1$<br>$a$        |                          |     |     |     |     |
| $L(c)$<br>$p(c)$ | $\infty$        | $2$<br>$a$        | $2$<br>$a$               |     |     |     |     |
| $L(d)$<br>$p(d)$ | $\infty$        | $2$<br>$a$        | $2$<br>$a$               |     |     |     |     |
| $L(e)$<br>$p(e)$ | $\infty$        | $\infty$          | $\infty$                 |     |     |     |     |
| $L(f)$<br>$p(f)$ | $\infty$        | $\infty$          | $\infty$                 |     |     |     |     |
| $L(g)$<br>$p(g)$ | $\infty$        | $\infty$          | $\color{yellow}7$<br>$b$ |     |     |     |     |
| $S$              | $\color{blue}a$ | $a,\color{blue}b$ |                          |     |     |     |     |

**Schritt 3**
![[Pasted image 20250103094233.png]]

| $L(a)$           | $0$      |            |                     |                          |     |     |     |
| ---------------- | -------- | ---------- | ------------------- | ------------------------ | --- | --- | --- |
| $L(b)$<br>$p(b)$ | $\infty$ | $1$<br>$a$ |                     |                          |     |     |     |
| $L(c)$<br>$p(c)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$          |                          |     |     |     |
| $L(d)$<br>$p(d)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$          | $2$<br>$a$               |     |     |     |
| $L(e)$<br>$p(e)$ | $\infty$ | $\infty$   | $\infty$            | $\color{yellow}3$<br>$c$ |     |     |     |
| $L(f)$<br>$p(f)$ | $\infty$ | $\infty$   | $\infty$            | $\infty$                 |     |     |     |
| $L(g)$<br>$p(g)$ | $\infty$ | $\infty$   | $7$<br>$b$          | $7$<br>$b$               |     |     |     |
| $S$              | $a$      | $a,b$      | $a,b,\color{blue}c$ |                          |     |     |     |
**Schritt 4**
![[Pasted image 20250103094446.png]]

| $L(a)$           | $0$      |            |            |                       |                          |     |     |
| ---------------- | -------- | ---------- | ---------- | --------------------- | ------------------------ | --- | --- |
| $L(b)$<br>$p(b)$ | $\infty$ | $1$<br>$a$ |            |                       |                          |     |     |
| $L(c)$<br>$p(c)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ |                       |                          |     |     |
| $L(d)$<br>$p(d)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ | $2$<br>$a$            |                          |     |     |
| $L(e)$<br>$p(e)$ | $\infty$ | $\infty$   | $\infty$   | $3$<br>$c$            | $3$<br>$c$               |     |     |
| $L(f)$<br>$p(f)$ | $\infty$ | $\infty$   | $\infty$   | $\infty$              | $\color{yellow}3$<br>$d$ |     |     |
| $L(g)$<br>$p(g)$ | $\infty$ | $\infty$   | $7$<br>$b$ | $7$<br>$b$            | $7$<br>$b$               |     |     |
| $S$              | $a$      | $a,b$      | $a,b,c$    | $a,b,c,\color{blue}d$ |                          |     |     |
**Schritt 5
![[Pasted image 20250103094604.png]]

| $L(a)$           | $0$      |            |            |            |                         |            |     |
| ---------------- | -------- | ---------- | ---------- | ---------- | ----------------------- | ---------- | --- |
| $L(b)$<br>$p(b)$ | $\infty$ | $1$<br>$a$ |            |            |                         |            |     |
| $L(c)$<br>$p(c)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ |            |                         |            |     |
| $L(d)$<br>$p(d)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ | $2$<br>$a$ |                         |            |     |
| $L(e)$<br>$p(e)$ | $\infty$ | $\infty$   | $\infty$   | $3$<br>$c$ | $3$<br>$c$              |            |     |
| $L(f)$<br>$p(f)$ | $\infty$ | $\infty$   | $\infty$   | $\infty$   | $3$<br>$d$              | $3$<br>$d$ |     |
| $L(g)$<br>$p(g)$ | $\infty$ | $\infty$   | $7$<br>$b$ | $7$<br>$b$ | $7$<br>$b$              | $7$<br>$b$ |     |
| $S$              | $a$      | $a,b$      | $a,b,c$    | $a,b,c,d$  | $a,b,c,d,\color{blue}e$ |            |     |
**Schritt 6**
![[Pasted image 20250103094743.png]]

| $L(a)$           | $0$      |            |            |            |             |                          |                          |
| ---------------- | -------- | ---------- | ---------- | ---------- | ----------- | ------------------------ | ------------------------ |
| $L(b)$<br>$p(b)$ | $\infty$ | $1$<br>$a$ |            |            |             |                          |                          |
| $L(c)$<br>$p(c)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ |            |             |                          |                          |
| $L(d)$<br>$p(d)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ | $2$<br>$a$ |             |                          |                          |
| $L(e)$<br>$p(e)$ | $\infty$ | $\infty$   | $\infty$   | $3$<br>$c$ | $3$<br>$c$  |                          |                          |
| $L(f)$<br>$p(f)$ | $\infty$ | $\infty$   | $\infty$   | $\infty$   | $3$<br>$d$  | $3$<br>$d$               |                          |
| $L(g)$<br>$p(g)$ | $\infty$ | $\infty$   | $7$<br>$b$ | $7$<br>$b$ | $7$<br>$b$  | $7$<br>$b$               | $\color{yellow}6$<br>$f$ |
| $S$              | $a$      | $a,b$      | $a,b,c$    | $a,b,c,d$  | $a,b,c,d,e$ | $a,b,c,d,e\color{blue}f$ |                          |
**Schritt 7**
![[Pasted image 20250103094743.png]]

| $L(a)$           | $0$      |            |            |            |             |                          |                            |
| ---------------- | -------- | ---------- | ---------- | ---------- | ----------- | ------------------------ | -------------------------- |
| $L(b)$<br>$p(b)$ | $\infty$ | $1$<br>$a$ |            |            |             |                          |                            |
| $L(c)$<br>$p(c)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ |            |             |                          |                            |
| $L(d)$<br>$p(d)$ | $\infty$ | $2$<br>$a$ | $2$<br>$a$ | $2$<br>$a$ |             |                          |                            |
| $L(e)$<br>$p(e)$ | $\infty$ | $\infty$   | $\infty$   | $3$<br>$c$ | $3$<br>$c$  |                          |                            |
| $L(f)$<br>$p(f)$ | $\infty$ | $\infty$   | $\infty$   | $\infty$   | $3$<br>$d$  | $3$<br>$d$               |                            |
| $L(g)$<br>$p(g)$ | $\infty$ | $\infty$   | $7$<br>$b$ | $7$<br>$b$ | $7$<br>$b$  | $7$<br>$b$               | $6$<br>$f$                 |
| $S$              | $a$      | $a,b$      | $a,b,c$    | $a,b,c,d$  | $a,b,c,d,e$ | $a,b,c,d,e\color{blue}f$ | $a,b,c,d,e,f\color{blue}g$ |

Aus dieser Tabelle entsthet auch ein Spannbaum (Dijkstra-Baum) (dieser ist hat aber nicht zwingend ein minimales Gewicht.)
![[Pasted image 20250103094927.png]]


