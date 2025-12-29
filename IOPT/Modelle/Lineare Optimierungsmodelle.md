Form:
max/min $\sum_{j=1}^{n}c_{j}x_{j}$
unter den Bedingungen
$$
\begin{align}
\sum_{j=1}^{n}a_{i,j}x_{j} y\leq b_{i},& i=1,\dots,r &(r<s\leq m) \\
\sum_{j=1}^{n}a_{i,j}x_{j}\geq b_{i} & ,i=r+1,\dots,s \\
\sum_{j=1}^{n}a_{i,j} =b_{i} & ,i =s+1,\dots,m \\
x_{j}>0,&j=1,\dots,p (p\geq n) \\
[x_{j}, \text{frei}, j=p+1,\dots,n]
\end{align}
$$

## Annahmen
- Zielfunktion: [[Funktionen|linear]], d.h. sowohl konvex wie auch konkav
- Konvexer Lösungsraum: ein [[Polyeder]]

-> Ein lokales Optimum ist ein globales Optimum
-> Ein Optimum, falls es eines gibt, kann immer (mindestens) in einem [[Extremalpunkt]] gefunden werden


## Voraussetzungen
### Proportionalität
- Der Beitrag (in der Zielfunktion oder in der rechten Seite einer Bedingung) einer Aktivität ist Proportional zu ihrer Grösse
- Genauer, für jede Variable muss gelten: Die Änderung im Funktionswert ist proportional zu Änderungen dieser Variable bei Fixierung aller anderen Variablenwerte
	- Variablen können nur mit "Exponent 1" vertreten sein
	- Das Produkt verschiedener Variablen ist möglich (aber solche Produkte sind nicht additiv)

### Additivität
- Jede Funktion (Zielfunktion oder rechten Seite einer Bedingung) ist die Summe von individuellen Beiträgen der Aktivitäten
- z.B. Ressourcenbelastung durch die Aktivitäten setzt sich zusammen aus der Summe der Belastungen durch die einzelnen Aktivitäten -> keine Wechselwirkungen erlaubt
- Fälle mit Wechselwirkung:
	- Komplementäre Produkte (z.B.: reduzierte Kosten bei Produktion / Werbung, Wechselwirkung bei Verkaufszahlen)
	- Produktion mit Reihenfolge abhängigem Rüstaufwand von einem Produkt zum anderen. (Bsp. Joghurtproduktion)

### Teilbarkeit der Variablen
- Solange die Entscheidungsvariablen alle Bedingungen erfüllen, dürfen sie beliebige Werte annehmen, d.h. auch nicht ganzzahlige Werte
- Variablenwerte in einer Optimallösung in der Regel nicht ganzzahlig
- Allerdings: bei gewissen speziellen Problemstrukturen: sog. natürliche Ganzzahligkeitseigenschaft:
	- z.B. bei Flussproblemen: Falls die Daten (Bedarfe, Angebote, Bogenkapazitäten, exklusiv Kosten) ganzzahlig sind, sind alle (Eckpunkt-)Lösungen ganzzahlig (von Bedeutung z.B. für das einfache Zuordnungsproblem)

### Sicherheit
- Der Wert jedes Parameters wird als eine bekannte Konstante angenommen
- In der Praxis ist diese Annahme selten erfüllt, da die Parameter (meist) gewisse Grössen über Vorgänge in der Zukunft angeben, was natürlich mit eine gewisse Unsicherheit belegt ist
- Sensitivitätsanalysen helfen diese Unsicherheit bis zu einem gewissen Grad abzufangen

## Einsatz
- Sehr effizient lösbar, auch für grosse Probleme (eine Million Variablen, Hunderttausende von Restriktionen (zudem: Dualität: Variable $\Leftrightarrow$ Restriktion)
- Software weit verbreitet: open source und kommerziell, für grössere Probleme muss (leider) meist auf kommerzielle Pakete zurückgegriffen werden
- Einsetzbarkeit von LP-Modellen: **mittel**
  Beschränkungen im Modelltypus und nicht in der Berechnung (siehe vorherige Folien)