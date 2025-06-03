>[!Definition]
>Ein **Punktschätzer** gib einen **einzelnen Wert** als Schätzung für einen unbekannten Parameter an.

**Beispiele**
- Der Mittelwert $\bar{x}$ einer [[Stichprobe]] als Schätzung für den wahren Mittelwert $\mu$ der Grundgesamtheit.
- Die [[Häufigkeitsanalyse#Relative Häufigkeit|relative Häufigkeit]] $h(x)$ in einer [[Stichprobe]] als Schätzung für die tatsächliche Wahrscheinlichkeit $P(x)$ in der Grundgesamtheit.

**Vorteil:** Einfach und direkt interpretierbar.
**Nachteil:** Enthält keine Information über die Unsicherheit der Schätzung.

## Kleinste Quadrate Schätzung $LSE$
Man macht keine Annahmen über die Verteilung in der Grundgesamtheit und zieht eine [[Stichprobe#Zufallsstichprobe|Zufallsstichprobe]] $x_{1},x_{2},\dots ,x_{n}$.

**Ziel:** Die Summe der quadrierten Fehler zwischen den beobachteten Werten und dem vorhergesagten Wert werden minimiert. Der Schätzer $\hat{\mu}$ für den Mittelwert $\mu$ einer Grundgesamtheit hat also die Eigenschaft, dass für die gegebene [[Stichprobe]] die Zahl:
$$
(x_{1}-\hat{\mu})^{2}+(x_{2}-\hat{\mu})^{2}+\dots+(x_{n}-\hat{\mu})^{2}
$$
minimal ist.

Mit Methoden der Analysis folgt:
$$
\hat{\mu}=\frac{1}{n}(x_{1}+ x_{2}+\dots+x_{n})
$$
Der Mittelwert $\hat{\mu}$ wird also mit dem Arithmetischen Mittel geschätzt.

## Mittelwert

$$
\hat{\mu}=\frac{1}{n}(x_{1}+ x_{2}+\dots+x_{n})
$$
## Varianz
**Varianz Schätzen der Grundgesamtheit**
$$
\hat{s}^{2} =\frac{1}{n-1}\sum_{i=1}^{n}(x_{i}-\bar{x})
$$
**Varianz Schätzung der Stichproben (nicht gebrauchen)**
$$
\hat{s}^{2} =\frac{1}{n}\sum_{i=1}^{n}(x_{i}-\bar{x})
$$