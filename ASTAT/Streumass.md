Die [[Häufigkeitsanalyse#Empirische Häufigkeitsverteilung| empirische Häufigkeitsverteilung]] beantwortet die Frage: Wie oft kommen die Werte eines Merkmals vor? Mit **statistischen Masszahlen** sollen nun spezifische Informationen aus den Daten herausgefiltert werden.

>[!info]
>Ein Streumass beschreibt mit einem typischen Wert, wie unterschiedlich die Ausprägungen eines Merkmals sind.

## [[Statistisches Merkmal|Nominale Merkmale]]
Wir wollen angeben, wie gleichmässig sich die ungeordneten Werte verteilen. Wenn bei einem Merkmal nur ein Wert vorkommt, gibt es keine Streuung. Wenn hingegen alle Werte eines Merkmals gleich häufig auftreten, gibt es maximale Unterschiedlichkeit. Als Mass für diese Charakteristik wird häufig der **Dispersionsindex**
$$
P = \frac{m}{m-1}(h(x_{1})\cdot(1-h(x_{1}))+h(x_{2})(1-h(x_{2}))+ \dots + h(x_{m})(1-h(x_{m})))
$$
gebraucht. Wenn $P>0.9$ ist, haben wir starke Dispersion und wenn $P<0.8$ ist haben wir geringe Dispersion.

Wenn im Extremfall ein Wert eine [[Häufigkeitsanalyse#Relative Häufigkeit|relative Häufigkeit]] von $h(x)=1.0$ hat, dann ist $P=0$.
Wenn alle Werte die gleiche relative Häufigkeit haben ist $P=1$

```python
werte,absH = np.unique(df["Geschlecht"],return_counts=True)
relH = absH / df.shape[0]
m = len(werte)
P = m/(m-1) * sum(rehlH*(1-relH))
```

## [[Statistisches Merkmal|Ordinale Merkmale]]
Wegen der natürlichen Reihenfolge können wird die Streuung differenziert beschreiben. Streuung ist gross, wenn die Werte gleichmässig beim kleinsten und beim grössten Wert des Merkmals liegen. Als Mass für diese Charakterisitk wird häufig die Diversität 
$$
D = \frac{4}{m-1}(H(x_{1})\cdot(1-H(x_{1}))+H(x_{2})\cdot(1-H(x_{2}))+\dots+H(x_{m})\cdot(1-H(x_{m})))
$$
gebraucht. Wenn $D > 0.8$ haben wir starke Diversität und wenn $D<0.6$ ist haben wir geringe Diversität. Wenn im Extremfall ein Wert eine relative Häufigkeit von $h(x) = 1$ hat, dann ist $D=0$ und wenn $50\%$ der Daten beim kleinsten und $50\%$ beim grössten Wert liegen, dann ist $D=1$.
```python
werte,absH = np.unique(df["Prädikat"],return_counts=True)
m = len(werte)
werte = np.array([werte[1],werte[2],werte[3],werte[0]])
absH = np.array([absH[1],absH[2],absH[3],absH[0]])
relH = absH/df.shape[0]
relSH = np.array([relH[0],sum(relH[:2]),sum(relH[:3]),sum(relH)])
D = 4/(m-1) * sum(relSH * (1-relSH))
```

## [[Statistisches Merkmal|Metrische Merkmale]]
Bei metrischen Daten sind die Quartile auch Zahlen. Daher können wir den Quartilsabstand $Q=x_{75}-x_{25}$ berechnen. In diesem Bereich liegen ungefähr $50\%$ der mittleren Daten. Wenn also $Q$ **klein** ist, dann liegen die Daten **eng beieinander** und wenn $Q$ **gross** ist, dann **streuen die Daten stark**. Der Quartilsabstand wird durch extrem Wert nicht gross beinflusst.

```python
Q = df["Alter"].quantile(0.75) - df["Alter"].quantile(0.25)
```

Ein anderes Mass für die Streuung ist die mittlere Abweichung $MD$ (oder $SD$ für Standard Deviation) der Daten vom arithmetischen Mittel.
$$
MD = \frac{1}{m}(\mid x_{1}-\bar{x}\mid +\mid x_{2}-\bar{x}\mid+\dots\mid x_{m}-\bar{x}\mid)
$$
```python
SD = sum(np.abs(df["Alter"]-df["Alter"].mean()))/len(df["Alter"])
> 7.84000
```

Weil die Absolutbeträge technische Schwierigkeiten mit sich bringen werden häufiger die **mittlere Quadratische Abweichung** $MQD$ vom arithmetischen Mittel
$$
MQD = \frac{1}{m}((x_{1}-\bar{x})^{2}+(x_{2}-\bar{x})^{2}+\dots+(x_{m}-\bar{x})^{2})
$$
```python
np.sqrt(1/len(df["Alter"]) * sum((df["Alter"]-df["Alter"].mean())**2))
> 160.69
```
verwendet.

Dieser Wert hat den Nachteil, dass die Dimension nicht mehr stimmt. Die Zahl $MQD$ hat quadratische Einhieten. Wenn wird aber aus $MQD$ die Wurzel ziehen erhalten wir die sogenannte Standardabweichung
$$
s=\sqrt{ MQD }
$$
bei der die Dimensionen wieder stimmt.
```python
df["Alter"].std(ddof=0)
```
