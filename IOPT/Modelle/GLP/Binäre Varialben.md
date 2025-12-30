Einsatz von binären Variablen
- Ja / Nein Entscheidungen
- Logische Ausdrücken
- Produkt von binären Variablen
- Entweder-Oder Entscheidungen
- Funktionen

## Ja / Nein Entscheid
- Aktivitäten, welche entweder ganz oder gar nicht durchgeführt werden

**Beispiel**
3 Lieferwagen mit Kapazitäten 20, 25, resp. 30 Tonnen können zur Belieferung eingesetzt werden.
$x_{i}$: 1, Fall Lieferwagen $i, i= 1,2,3$ eingesetzt wird, sonst 0

## Logische Ausdrücke
Gegeben: eine Menge P von Projekten.
Es soll für jedes Projekt entschieden werden, ob es durchgeführt wird oder nicht.
=> binäre Variable pro Projekt.

### Auswahlbeschränkung
Nun ist es aber so beschränkt, dass nur $r$ Projekt durchgeführt werden darf:
$$
\sum_{i\in P}x_{i}\leq r
$$
### [[Implikation (Subjunktion)|Implikation]]
Falls Projekt $i$ durchgeführt wird, dann muss Projekt $j$ auch durchgeführt werden:
$$
x_{j}\geq x_{i}
$$
#### Negation
Falls Projekt $i$ durchgeführt wird, dann darf Projekt $j$ nicht durchgeführt werden: 
$$
x_{i} + x_{j} \leq 1
$$
#### Mit 3 Variablen
Falls Projekt $i$ durchgeführt wird, dann muss Projekt $j$  und $k$ auch durchgeführt werden:
- Zwei bedingungen. Es muss gelten $x_{j}\geq x_{i}$ **und** $x_{k}\geq x_{i}$

##### Order
Falls Projekt $i$ durchgeführt wird, dann muss Projekt $j$ oder (beide) $k$ auch durchgeführt werden:
$$
x_{j} + x_{k} \geq x_{i}
$$
oder 
$$
x_{j} + x_{k} = x_{i}
$$
#### Umkehrung
Falls entweder Projekt j oder k (oder beide) durchgeführt werden, dann
muss Projekt i durchgeführt werden:
$$
x_{i}\geq x_{j} \text{ und } x_{i} \geq x_{k}
$$

Falls beide Projekte j und k durchgeführt werden, dann muss Projekt i
durchgeführt werden:
$$
 x_{i} \geq x_{j}+x_{k}-1
$$
## Produkt von binären Variablen
Gegeben sind drei binäre entscheide $x_{1},x_{2},x_{3}$.

Modelliere die Gleichung $x_{3}=x_{1} \cdot x_{2}$ mit linearen Bedingungen:
1. $x_{3}\leq x_{1}$
2. $x_{3}\leq x_{2}$
3. $x_{3}\geq x_{1}+x_{2}-1$
![[binäreVariablen.png]]

## Entweder Oder Entscheide
In gewissen Situationen muss entweder eine Bedingung A oder eine Bedingung B (oder beide) erfüllt werden:

minimiere $z=x_{1}+x_{2}$ unter den Bedingungen
$$
\begin{align}
x_{1}&\geq o \\
x_{2} & \geq0 \\
2x_{1}+x_{2}\geq 6 & \text{ oder } x_{1}+2x_{2}\geq 7
\end{align}
$$
![[binäreVariablen2.png]]


1. Einführen einer binären Entscheidungsvariable y Bedeutung: y = 1 falls 1) erfüllt wird und sonst 0, d.h. 2) muss erfüllt sein:
	   minimiere $z=x_{1}+x_{2}$ unter den Bedingungen
	   $x_{1}\geq 0, x_{2}\geq 0$
	   $2x_{1}+x_{2}\geq 6y$
	   $x_{1}+2x_{2}\geq 7(1-y)$
	   
	Allgemein (rechte Seite):
		$6-My$
		$7-M(1-y)$
	   $M \to$ grosse konstante Zahl

## Funktionen

### Modellierung von Fixkosten
Bei der Modellierung von Fixkosten gibt es eine Entscheidungsvariable $x$ welche die Produktionsmenge angbit. 
Die Produktionskosten werden mit einer Sprungfunktion $f(x)=\begin{cases}0 \text{ falls }x= 0 \\ a+bx \text{ falls } x>0\end{cases}$
modelliert. Diese Funktion ist nicht linear.

1. Führe Entscheidungsvariable $y$ ein: $y=1$ falls eine positive Menge produziert wird und $0$ sonst.
2. Es muss nun gelten $x\leq My$. Dabei ist $M$ eine Konstante.
3. Funktion $f(x)$ kann nun wie folgt modelliert werden: $f(x)=ay+bx$
### Ordered Set of Type 1
![[OrderedSetOfType1.png]]
1. Es wird eine Entscheidungsvariable eingeführt, die angibt welche Menge gekauft wird. $x$
2. Falls die Menge von $x$ einer gewissen Anzahl übersteigt, wird ein anderer Rabatt gewährt.
3. Führe pro Rabatt-Sektor eine binäre Variable $y_{i}$ ein, welche angibt, ob wird den Stückpreis in Sektor $i$ bezahlen.
4. Führe pro Rabatt-Sektor eine kontinuierliche Entscheidungsvariable $x_{i}$ ein, wobei $x_{i}$ die Menge angibt, welche wir zum Einheitspreis $a_{i}$ erhalten.
5. Nun müssen folgende Bedingungen gelten:
$$
\begin{align}
x&=x_{1}+x_{2}+x_{3} \\
1 & =y_{1}+y_{2}+y_{3} \\
b_{i-1}\times y_{i}\leq &x_{i}\leq b_{i}\times y_{i}
\end{align}
$$
6. Die Kostenfunktion ist dann $f(x)=a_{1}x_{1}+a_{2}x_{2}+a_{3}x_{3}$
