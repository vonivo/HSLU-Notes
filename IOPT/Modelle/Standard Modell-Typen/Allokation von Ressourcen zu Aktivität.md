**Ressourcen** $i=1,\dots,m$ (Personal, Betriebsmittel) müssen auf **Aktivitäten** $j=1,..,n$ (Produktion, Transport, Investition) zugeteilt werden.

1. Variable $x_{j}$ welche das Niveau/Intensität der Aktivität angibt ($j=1,2,\dots m$)
2. Daten
	1. $b_{i}$ stellt die verfügbare Menge / Kapazität der Ressource $i$ dar. ($i=1,\dots,m$)
	2. $a_{i,j}$: Menge welche von Ressource $i$ benötigt wird um Aktivität $j$ auszuführen. $i=1,\dots,m$ und $j=1,\dots,n$
	3. $c_{j}$: Zielbeitrag welche eine Einheit der Aktivität $j$ generiert. $j=1,\dots,n$

## Modell
maximiere $\sum_{j=1}^{n}c_{j}x_{j}$ unter den Bedingungen
$$
\begin{align}
\sum_{j=n}^{n}a_{i,j}x_{j} &\leq b_{i} & \text{für alle} i=1,\dots,m \\
	x_{j} & \geq 0 & \text{für alle }j=1,\dots,n
\end{align}
$$

### Technologie Matrix
$A = \{ a_{i,j}: i=1,\dots,m; j =1,\dots,n \}$ 

![[TechnologieMatrix.png]]