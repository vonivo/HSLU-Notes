## Beispiel: Krankenpfleger
- Eine Woche, vier Krankenpfleger
- Drei Schichten à 8 Stunden
- Bedarf von 1 Pfleger pro Schicht und Tag

**Bedingungen**
- Für jeden Pfleger eine Schicht pro Tag oder frei
- Jeder Pfleger arbeitet zwischen 5 und 6 Schichten insgesamt
- Bedarf an Pfleger genau gedeckt (ein Pfleger pro Schicht)
- Über die ganze Woche, höchstens zwei unterschiedliche Pfleger in einer Schicht
- Falls ein Pfleger Schicht 2 oder 3 an einem Tag arbeitet, muss er auch die gleiche Schicht am vorhergehenden oder nächsten Tag arbeiten

**Entscheidungsvariablen**
- Für jeden Pfleger $n=0,\dots,nMax$ und jeden Tag $d=0,\dots dMax$ und jede Schicht $s=0,\dots ,sMax$ führe eine Variable $x_{n,d,s}$ ein:
$$
x_{n,d,s}=1\text{ falls Pfleger n am Tag d Schicht s macht, sonst 0}
$$
- Für jeden Pfleger $n=0,\dots,nMax$ und jede Schicht $s=1,\dots,sMax$ führe eine Variable $y_{n,s}$ ein:
$$
y_{s,n}= \text{1 falls Schicht s durch Pfleger n gemacht werden darf (an beliebigen Tag)}
$$



**Bedinungen**
1. Für jeden Pfeger $n$ eine Schicht an jedem Tag oder Frei:
$$
\sum_{s=0}^{sMax}x_{n,d,s}=1 \text{  für alle n,d}
$$
2. Jeder Pfleger arbeitet zwischen 5 und 6 Schichten insgesamt (=1 oder 2 Tage frei)
$$
1\leq \sum_{d=0}^{dMax}x_{n,d,0} \leq 2 \text{ für alle n}
$$
3. Bedarf an Pfleger genau gedeckt (nur ein Pfleger pro Schicht)
$$
\sum_{n=0}^{nMax}x_{n,d,s}=1 \text{ für alle d und }s=1,\dots,sMax
$$
=> Schicht 0 wird nicht gezählt da diese **frei ist**.
4. Über die ganze Woche, höchstens zwei unterschiedliche Pfleger in einer Schicht
$$
\sum_{n=0}^{nMax}y_{s,n}\leq 2 \text{ für s}=1,\dots,0
$$
5. Falls ein Pfleger Schicht 2 oder 3 an einem Tag arbeitet, muss er auch die gleiche Schicht am vorhergehenden oder nächsten Tag arbeiten
$$
\begin{align}
\text{Falls:} x_{n,d,s} = 1 \text{ dann }x_{n,d-1,s}+x_{n,d+1,s}\geq 1\\
\text{für alle n}=0,\dots,nMax ;d=0,\dots ,dMax; s=2,3
\end{align}
$$
6. Falls $y_{s,n}=0$ dann $x_{n,d,s}=0$ für alle $n,d,s$

**Implementation**
![[CP_NurseScheduling_Code1.png]]![[CP_NurseScheduling_Code2.png]]

## Job Scheduling
![[CP_JobScheduling.png]]
Gegeben:
- Aufträge $a=0,\dots,n-1$
- Maschinen $m=0,\dots,r-1$
- Jeder Auftrag muss in einer gegebenen Reihenfolge auf den Maschinen bearbeitet werden; Eine Bearbeitung eines Auftrags auf einer Maschine heisst Operation /Arbeitsgang 
- Jede Operation hat eine Operationszeit / Bearbeitungsdauer
- Eine Maschine kann nicht mehr als eine Operation auf einmal bearbeiten
- Eine Operation darf nicht unterbrochen werden
- Alle Aufträge können zum Zeitpunkt 0 starten

**Gesucht**
Finde einen zulässigen Ablaufplan, sodass die (Gesamt-) Zykluszeit (sog. „Makespan“) minimal ist


**Entscheidungsvariable**
Für jede Operation $i=0,\dots,maxO$
- $x_{i}$ Startzeitpunkt der Operation $i$
- $y_{i}$ Endzeitpunkt der Operation $i$
=> Verknüpfung von $x_{i}$ und $y_{i}$ durch Intervallvariablen (IV).
$$
IV(x_{i},d_{i},y_{i})
$$
wobei $d_{i}$ die konstante Dauer der Operation ist.

- Variable $z$ Ende der Bearbeitung -  Wertebreich $: \{ 0,\dots,H \}$

**Bedingungen**
- **Präzedenzbedingungen** innerhalb eines Auftrages: Für alle Paare von Operationen $i$ und $j$, die einander folgen in einem Auftrag muss gelten: $x_{i}\leq y_{i}$
- Auf jeder Maschine m müssen ‘ihre’ Operationen nicht überlappend eingeplant werden. **Implementation mit den Intervallvariablen und globale Constraint**
  $\text{noOverlap(IV(}x_{i},d_{i},y_{i}) i\in \{ 0,\dots,oMax\text{ mit }m_{i}=m\}$

**Code**
![[CP_JobScheduling_Code1.png]]![[CP_JobScheduling_Code2.png]]
![[CP_JobScheduling_Code3.png]]
