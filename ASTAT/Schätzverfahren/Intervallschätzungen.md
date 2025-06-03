>[!Definition]
>Ein **Intervallschätzer** gibt einen **Intervall** an, in dem der wahre Parameter mit einer bestimmten Wahrscheinlichkeit liegt.

**Beispiele**
- Ein $95\%$-**Konfidenzintervall** $[x_{min},x_{max}]$ für den Mittelwert gibt an, in welchem Bereich der wahre Mittelwert der Grundgesamtheit mit einer Wahrscheinlichkeit von $95\%$ liegt.

**Vorteil:** Enthält Informationen über die Unsicherheit der Schätzung.
**Nachteil:** Komplexer als ein einzelner Punkt.

Bei der Intervallschätzung wird für einen unbekannten Parameter $\theta$ zunächst aus einer Stichprobe eine Punktschätzung $\hat{\theta}$ berechnet, um die herum dann ein (meist symmetrisches) **Konfidenzintervall** konstruiert wird:
$$
K=[\hat{\theta}-\delta_{n}, \hat{\theta}+\delta_{n}]
$$
Dabei wird $\delta$ so bestimmt, dass das Konfidenzintervall den unbekannten Parameter $\theta$ mit einer vorgegebenen Wahrscheinlichkeit überdeckt.


Die Wahrscheinlichkeit $\alpha$ wird Konfidenzniveau genannt. (Meist $99\%$ oder $95\%$).


## Bootstrapverfahren
Um $\delta$ zu bestimmen, kann der Bootstrap-Algorithmus verwendet werden:
1. Ziehe eine [[Stichprobe#Zufallsstichprobe|Zufallsstichprobe]] (Resample) mit Zurücklegen aus dem bestehenden Sample der Grösse $n$.
2. Erfasse den im Fokusstehende Parameter für das Resample.
3. Wiederhole Schritt 1 & 2 viele Male.
4. Zur Ermittlung des $\alpha\%$-Konfidenzintervalls müssen wir nun
$$
\left( \frac{100-\alpha}{2} \right)\%
$$
	der **geordneten** Werte des Resamples an beiden Enden abschneiden.
5. Die zwei Werte an den geordneten Enden ergeben nun das Konfidenzintervall.