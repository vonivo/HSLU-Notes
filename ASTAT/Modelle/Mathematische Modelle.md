**Daten** und **Zufallsprozesse** sind eng miteinander verbunden, weil Daten oft als Beobachtung von zufälligen Vorgängen betrachtet werden.
- Eine Zufallsvariable $X$ beschreibt die möglichen Werte eines Zufallsexperiments (z.B. die Körpergrösse einer zufällig gewählten Person). Wenn wir Messungen durchführen, erhalten wir konkrete Werte $x$ die als Realisierung der Zufallsvariablen $X$ gelten.
- Die zugrunde liegende **Wahrscheinlichkeitsverteilung** einer Zufallsvariablen hilft, die Struktur der Daten zu verstehen. Statistische Modelle nutzen diese Verteilungen um Vorhersagen oder Schlussfolgerungen zu ermöglichen.
- Aus Stichprobendaten werden Parameter geschätzt, um Rückschlüsse auf die zugrunde liegende Zufallsvariable und deren Verteilung zu ziehen.

Zusammenfassend sind Zufallsvariablen mathematischer Modelle für die Prozesse, die Daten erzeugen. Daten wiederum liefer beobachtbare Werte, hie helfen die zugrunde liegenden Wahrscheinlichkeitsverteilungen zu verstehen und in der Statistik zu nutzen.

## Beispiel
Wenn wir **mehrmals einen Würfel werfen**, erzeugen wir Daten. Wir können zählen, wie oft jede Zahl erscheint und die relative Häufigkeit für jede Zahl bestimmen:
```python 
import numpy as np

anzWürfe = 1000000
würfe = np.array([randint(1,6) for _ in range(anzWürfe)])
werte, absH = np.unique(würfe,return_counts=True)
relH = absH/anzWürfe
for i in werte:
    print("relative Häufigkeit der Augenzahl",i,":",relH[i-1])
```
```
relative Häufigkeit der Augenzahl 1 : 0.166224
relative Häufigkeit der Augenzahl 2 : 0.166214
relative Häufigkeit der Augenzahl 3 : 0.167592
relative Häufigkeit der Augenzahl 4 : 0.166834
relative Häufigkeit der Augenzahl 5 : 0.166188
relative Häufigkeit der Augenzahl 6 : 0.166948
```
Wenn wir davon ausgehen, dass wir einen **fairen Würfel** werfen, können wir dieses Zufallsexperiment mit einer Zufallsvariable modelieren:
$$
\begin{align}
X(\text{Eins}) &=1 \\
X(\text{Zwei}) &=2 \\
X(\text{Drei}) &=3 \\
X(\text{Vier}) &=4 \\
X(\text{Fünf}) &=5 \\
X(\text{Sechs}) &=6
\end{align}
$$
Wenn wir einen fairen Würfel werfe, verteilt sich die Augenzahlen perfekt symmetrisch:

| $x$      | $1$            | $2$            | $3$            | $4$            | $5$            | $6$            |
| -------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- |
| $P(X=x)$ | $16.\bar{6}\%$ | $16.\bar{6}\%$ | $16.\bar{6}\%$ | $16.\bar{6}\%$ | $16.\bar{6}\%$ | $16.\bar{6}\%$ |
Genau so, wie wir die Summenhäufigkeiten berechnet haben, können wir nun auch für dies Wahrscheinlichkeiten die **kumulative Wahrscheinlichkeitsverteiliung** angeben: $$\begin{array}{c|cccccc}x&1&2&3&4&5&6\\ \hline P(X\leqslant x)&16.\overline{6}\%&33.\overline{3}\%&50\%&66.\overline{6}\%&83.\overline{3} &100\%\end{array}$$ <br> Mit diesen Verteilungen können wir auch angeben, wie gross zum Beispiel die Wahrscheinlichkeit ist, dass wir eine Zahl zwischen 2 und 5 würfeln:
$$P(2<X<5) = P(X=3) + P(X=4) = 16.\overline{6}\% + 16.\overline{6}\% = 33.\overline{3}\%$$
oder mit den kumulativen Wahrscheinlichkeiten
$$P(2<X<5) = P(X\leqslant 4) - P(X\leqslant 2) = 66.\overline{6}\% - 33.\overline{3}\% = 33.\overline{3}\%\;.$$
Aus den Daten haben wir die mittlere Lage und die Streuung berechnet. Diese Masse können wir auch im Modell bestimmen. Dem arithmetischen Mittel für die [[Lagemass|Lage]] entspricht der sogenannte [[Erwartungswert]] $\mu$ der [[Zufallsvariable]] $X$
$$ \begin{align*}\mu &= P(X=1)\cdot 1 + P(X=2)\cdot 2 + \ldots + P(X=6)\cdot 6 \\
&=\frac{1}{6}\cdot 1 +\frac{1}{6}\cdot 2 + \frac{1}{6}\cdot 3 + \frac{1}{6}\cdot 4 + \frac{1}{6}\cdot 5 + \frac{1}{6}\cdot 6  = 3.5\end{align*}$$  
und der [[Streumass|mittleren Quadratischen Abweichung]] entspricht die sogenannte **Varianz** $\sigma^2$ der Zufallsvariablen $X$
$$ \begin{align*}\sigma^2 &= P(X=1)\cdot (1-\mu)^2 + P(X=2)\cdot (2-\mu)^2 + \ldots + P(X=6)\cdot (6-\mu)^2 \\
&=\frac{1}{6}\cdot (1-3.5)^2 +\frac{1}{6}\cdot (2-3.5)^2 + \ldots + \frac{1}{6}\cdot (6-3.5)^2  = 2.91\overline{6}\end{align*}$$ beziehungsweise die **Standardabweichung** $$\sigma = \sqrt{2.91\overline{6}} = 1.7078\dots\;.$$

Auch die $p$-**Quantile** können wir bei Zufallsvariablen $X$ aus der kumulativen Wahrscheinlichkeitsverteilung bestimmen. Das $p$-Quatil $x_p$ ist die Zahl mit der Eigenschaft $$P(X\leqslant x_p)\geqslant p \quad\text{ und }\quad P(X\geqslant x_p)\geqslant 1-p\;.$$
Also zum Beispiel ist beim Würfel das 75\%-Quantil die Augenzahl 5, weil
$$P(X\leqslant 5)= 83.\overline{3}\%\geqslant 75\% \quad\text{ und }\quad P(X\geqslant 5) = 100\%-P(X<5) =33.\overline{3}\% \geqslant 25\%\;.$$

## Mathematische Modelle der Zufallsverteilung
- [[Diskrete uniforme Verteilung]]
- [[Bernoulli Verteilung]] (siehe DMATH: [[Bernoulliverteilung]])
- [[Binomial Vertielung]] (siehe DMATH: [[Binomialverteilung]])
- [[Poisson Vertielung]] (siehe DMATH: [[Poissonverteilung]])
- [[Hypergeometrischesverteilung]] (siehe DMATH: [[Hypergeometrisches Verteilung]])
- [[Stetige uniforme Verteilung]]
- [[Exponentialverteilung]]
- [[Normalverteilung]]