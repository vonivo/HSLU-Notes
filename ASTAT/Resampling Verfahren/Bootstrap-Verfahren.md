1. Ziehe eine [[Stichprobe#Zufallsstichprobe|Zufallsstichprobe]] (Resample) mit Zurücklegen aus dem bestehenden Daten der Grösse $n$.
2. Erfasse den im Fokusstehende Parameter für das Resample.
3. Wiederhole Schritt 1 & 2 viele Male.
4. Zur Ermittlung des $\alpha\%$-Konfidenzintervalls müssen wir nun
$$
\left( \frac{100-\alpha}{2} \right)\%
$$
	der **geordneten** Werte des Resamples an beiden Enden abschneiden.
5. Die zwei Werte an den geordneten Enden ergeben nun das Konfidenzintervall.
```python
df = pd.read_csv("Daten/loans_income.csv")

meanIncomes = []
stds = []
for i in range(1000):
	sample = df['x'].sample(128, replace=True)
	meanIncome.append(sample.mean())
	std.append(sample.std(ddof=0))
    meanIncomes.append(meanIncome)
    stds.append(std)

lower_bound_1 = np.percentile(meanIncomes, 2.5)
upper_bound_1 = np.percentile(meanIncomes, 97.5)
lower_bound_2 = np.percentile(stds, 0.5)
upper_bound_2 = np.percentile(stds, 99.5)
```