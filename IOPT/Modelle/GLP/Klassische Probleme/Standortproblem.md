Das Standortproblem ist ein Problem der [[Ganzzahlig Lineare Programmierung]].

Entscheide über Standorte von neuen Anlagen, um Kunden optimal zu bedienen.

Geben:
- Menge $F$ von $n$ möglichen Fabriken.
- Öffnungskosten $r_{f}$ für jede Fabrik $f\in F$.
- Menge von $C$ Kunden.
- Transportkosten $d_{c,f}$ wenn Kunde $c\in C$ von Fabrik $f\in F$ bedient wird.

**Problem**
Wähle eine Untermenge der zu öffnenden Fabriken und weise jedem Kunden genau eine geöffnete Fabrik zu, sodass die Summe der Öffnungs- und Transportkosten minimal ist.

1. Führe folgende [[Binäre Varialben]] ein:
	1. $y_{f}$: 1 Falls Fabrik $f\in F$ eröffnet wird.
	2. $x_{c,f}$: 1 Falls Kunde $c\in C$ durch Fabrik $f\in F$ bedient wird.

**Modell**
$$
\begin{align}
\text{min} & \sum_{f\in F}r_{f}y_{f} + \sum_{c\in C}\sum_{f\in F}d_{c,f}x_{c,f} \\
\text{unter den Bedinungen:} \\
 & \sum_{f\in F}x_{c,f} = 1 & \text{für alle }c\in C \\
 & x_{c,f} \leq y_{f} & \text{ für alle }c\in C \text{ und }f\in F \\
& x_{c,f}, y_{f} \in \{ 0,1 \}
\end{align}
$$

