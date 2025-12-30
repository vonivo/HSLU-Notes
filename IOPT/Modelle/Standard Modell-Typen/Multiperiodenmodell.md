Ein Multiperiodenmodell beurteilt ein Problem mit einem Zeithorizont über mehrere Peridoen.

Dies könnte z.B. ein Investitionsentscheid oder die Lagerhaltung in Produktion und Distribution sein.

Diese Modell wird oft mit [[Allokation von Ressourcen zu Aktivität]] oder [[Überdeckungsproblem]] kombiniert.


## Beispiel 1
Wir haben $2200.-$ CHF als Startkapital verfügbar am 1. Jahres.
Am Anfang jedes Jahres $t = 1,..,5$ kann in 3 Typen von Anlagen investiert werden:

| Anlage-Typ | Dauer     | Zins |
| ---------- | --------- | ---- |
| 1          | 1-Jährig  | 2.0  |
| 2          | 2-Jähjrig | 2.5  |
| 3          | 3-Järig   | 3.0  |
Die Zinsauszahlungen erfolgen jeweils am Jahresende.

**Problem**
Wie anlegen, damit am Ende des Jahres t = 5 ein maximales Kapital verfügbar ist?

**Strategie**:
Geld welches frei wird (Anlage + Zins) sofort wieder anlegen.

1. $x_{i,t}$ ist der Betrag welcher in Anlage $i$ in Periode $t$ angelegt wird. $i=1,2,3$
2. Aufstellen der Bilanzgleichung zum Zeitpunkt $t$:
	1. Ausstehnde Zahlungen aus fürheren Investitionen
		- $1.03x_{3,t-3}$
		- $0.03x_{3,t-2}$
		- $0.03x_{3,t-1}$
		- $1.025x_{2,t-2}$
		- $0.025x_{2,t-1}$
		- $1.02x_{1,t-1}$
	2. Investitionen für das neue Jahr:
		- $x_{3,t}$
		- $x_{2,t}$
		- $x_{1,t}$
$$
\begin{align}
&1.03x_{3,t-3} + 0.03x_{3,t-2} +0.03x_{3,t-1} \\
&+1.025x_{2,t-2}+0.025x_{2,t-1} \\
&+1.02x_{1,t-1} &= x_{3,t}+x_{2,t}+x_{1,t}
\end{align}
$$

## Modell
Maximiere $1.03x_{3,3} + 0.03x_{3,4} +0.03x_{3,5} +1.025x_{2,4}+0.025x_{2,5}+1.02x_{1,5}$
unter den Bedingungen:
$$
\begin{align}
x_{3,1}+x_{2,1}+x_{1,1} &= 2200 \\
0.03x_{3,1} + 0.025x_{2,1}+1.02x_{1,1}- x_{3,2}+x_{2,2}+x_{1,2} &= 0 \\
0.03x_{3,1} + 0.03x_{3,2} +1.025x_{2,1}+ 0.025x_{2,2}+1.02x_{1,2}- x_{3,3}+x_{2,3}+x_{1,3} &= 0 \\
1.03x_{3,1} + 0.03x_{3,2} + 0.03x_{3,3} +1.025x_{2,2}+ 0.025x_{2,3}+1.02x_{1,3}- x_{3,4}+x_{2,4}+x_{1,4} &= 0 \\
1.03x_{3,2} + 0.03x_{3,3} + 0.03x_{3,4} +1.025x_{2,3}+ 0.025x_{2,4}+1.02x_{1,4}- x_{3,5}+x_{2,5}+x_{1,5} &= 0
\end{align}
$$


## Beispiel 2: Lagerhaltung
Dilemma des Produzenten: Bei variablem Bedarf, auf Vorrat montieren oder bei Spitzenbedarf Überstunden leisten?

- Eine Abteilung montiert 3 Produkte $i =1,2,3$.
- Der Bedarf für die 4 nächsten Quartale („Perioden“) $t = 1,\dots,4$, wurde geschätzt und beträgt $d_{i,t}$, $i=1,2,3$, $t=1,\dots,4$.
- Die Montage einer Einheit von $i$ benötigt $k_{i}$ Arbeitsstunden.
- In jeder Periode $t$ sind $b_{t}$ reguläre Arbeitsstunden verfügbar.
- Der Abteilungsleiter erwägt Überstunden. Die Überstunden kosten $h_{t}$ Fr.- pro Std. und sollen 0.2 × $b_{t}$, $t = 1,\dots,4$, nicht überschreiten (die Überstunden sollen höchstens 20% der regulären Arbeitsstunden ausmachen)
- Es ist möglich, mehr als den Bedarf zu montieren und zu lagern. Falls $y_{i,t}$ Einheiten des Produkts $i$ am Lager am Ende der Periode $t$ sind, fallen für die Periode Kosten $f_{it} \times y_{i,t}$ an.
- Die (bekannten) Anfangslagerbestände zu Beginn der ersten Periode sind $y_{i,0}$, $i =1,2,3$
- Das Entscheidungsproblem: Wie montieren in den 4 Perioden, so dass der Bedarf gedeckt ist, die Überstunden-Bedingungen eingehalten sind und minimale totale (Lager- und Überstunden-)Kosten anfallen

**Entscheidungsvariable**
1. $x_{i,t}$ Produktionsmenge des Produkts $i$ in Periode $t$
2. $v_{t}$ Anzahl Überstunden in Periode $t$

**Konsequenzvariablen**
1. $y_{i,t}$ Menge von $i$ an Lager am Ende der Periode $t$

**Bilanzgleichung**
$$
y_{i,t-1} + x_{i,t} = y_{i,t}+d_{i,t}
$$
### Modell
Minimiere $\sum_{i=1}^{3}\sum_{t=1}^{4} f_{i,t}\times y_{i,t} + \sum_{t=1}^{4}h_{t}*v_{t}$ unter den Bedingungen
$$
\begin{align} \\
\sum_{i=1}^{3}x_{i,t}k_{i} - v_{t} &\leq b_{t} & \text{für alle Perioden}\\
v_{t}&\leq 0.5b_{t} & \text{für alle Perioden }\\
x_{i,t}+y_{t-1}-y_{t}& \geq d_{i,t} & \text{für alle Perioden und Produkte} \\
	x_{i,t} & \geq 0 \\
v_{t} & \geq 0 \\
y_{ti,t}&\geq 0
\end{align}
$$