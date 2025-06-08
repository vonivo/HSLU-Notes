Bei einer [[Regressionsanalyse]] ist es sinvoll ein Teil der ursprünglichen Daten beseitezulegen und sie nicht zur Anpassung des Modells zu verwenden.

Somit kann die [[Modellbewertung]] mit "out-of-Sample" Daten durchgeführt werden.

**Ablauf:**
- Lege $\frac{1}{k}$ der Daten als **Hold-out-Stichprobe** beseite.
- Trainiere das Modell mit den übrigen Daten.
- Wenden das Modell auf die **Hould-out-Stichprobe** an und berechne den **Root-Mean-Square-Error**
$$
RMSE=\sqrt{ \frac{r_{1}^{2}+r_{2}^{2}+\dots+r_{n}^{2}}{n} }
$$
- Wiederhole diese Schritte, bis alle Daten einmal **Hold-Out** war.
- Bilde den Mittelwert der $RMSE$.
