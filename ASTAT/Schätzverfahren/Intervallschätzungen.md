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
Um $\delta$ zu bestimmen, kann das [[Bootstrap-Verfahren]] verwendet werden: