>[!info]
>Eine reelle Zahlenfolge ($a_n$) ist eine Abbildung von $\mathbb{N}$ nach $\mathbb{R}$, die jedem $n \in \mathbb{R}$ ein $a_{n} \in \mathbb{R}$ zuordnet. Man schreibt:
>$$
>(a_{n}) = a_{1}, a_{2},a_{3}, \dots, a_{n}, \dots
>$$
>Die reellen Zahlen $a_{n}$ heissen Glieder der Folge, $a_{n}$ ist das $n$-te Glied der Folge $(a_{n})$. Eine reelle Zahlenfolge wird auch kurz Folge genannt.

Eine Folge kann beschrieben werden druch:
- **die Aufzählung ihrer Glieder**,
- **das Bildungsgesetz**, d. h. die Funktionsvorschrift, nach welcher aus $n$ das $n$-Glied $(a_{n})$ berechnet werden kann,
- **eine Rekursionsvorschrift**, nach welcher das Glied $a_{n}$ berechnet werden kann, sobald einige oder alle vorherigen Glieder $a_{k} \space (k \lt n)$ bekannt sind.

### Beispiele
- $(a_{n}) = -\frac{1}{2}, -\frac{1}{4},-\frac{1}{6}\dots$ Bildungsgesetz: $a_{n}=-\frac{1}{2n}$
- $(a_{n}) =1^3, 2^3,3^3,\dots$ Bildungsgesetz: $a_{n}=n^3$
- $(a_{n}) =0,\frac{1}{2}, \frac{2}{3},\frac{3}{4},\dots$ Bildungsgesetz: $a_{n}=\frac{n-1}{n}=1-\frac{1}{n}$

## Rechnen mit Folgen
- Eine Folge $(a_{n})$ multipliziert man mit einer reellen Zahl $\lambda$, indem man jedes Glied der Folge mit dieser Zahl multipliziert:
$$
\lambda(a_{n}) = (\lambda a_{n})
$$
- Zwei folgen $(a_{n})$ und $(b_{n})$ addiert man, indem man entsprechende Glieder addiert:
$$
(a_{n}) + (b_{n}) = (a_{n} + b_{n})
$$
- Eine Folge $(a_{n})$ heisst **konstante Folge**, falls $a_{n} = c \in \mathbb{R}, \forall n \in \mathbb{N}$.
	- Für eine [[Arithmetische Folge]] bedeutet dies $d=0$
	- Für eine [[Geometrische Folge]] bedeutet dies $q=1$
	

## Eigenschaften
Ähnlich wie bei Funktionen wird die [[Wachstumsverhalten|Zu- und Abnahme]] betitelt:
- Eine Folge $(a_{n})$ heisst **(streng) monoton zunehmend**, falls $(a_{n+1} \gt a_{n})$ $a_{n+1}\ge a_{n}, \forall n \in \mathbb{N}$. Jedes Glied ist (streng) grösser als das vorherige.
- Analog wird **(streng) monoton abnehmend** definiert.
- Eine Folge $(a_{n})$ heisst **beschränkt**, falls eine positive Zahl $c$ existiert mit $\lvert a_{n} \rvert\le c, \forall n$. Alle Glieder der Folge liegen im Graphen unter einem *Teppich* der Breite $2c$ Andernfalls heisst die Folge $(a_{n})$ unbeschränkt.