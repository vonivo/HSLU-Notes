Die [[Häufigkeitsanalyse#Empirische Häufigkeitsverteilung| empirische Häufigkeitsverteilung]] beantwortet die Frage: Wie oft kommen die Werte eines Merkmals vor? Mit **statistischen Masszahlen** sollen nun spezifische Informationen aus den Daten herausgefiltert werden.

>[!info]
>Das **Lagemass** beschreibt mit einem typischen [[Statistisches Merkmal|statistisches Merkmal|Wert]], wo die Ausprägung eines Merkmals liegen.

## [[Statistisches Merkmal|Nominale Merkmale]]
Weil die Werte keine natürliche Reihenfolge haben können, **kann keine Mitte festgelegt werden**. Als repräsentativer Wert für die Lage der Werte wird oft der **häufigste Wert** (grösste [[Häufigkeitsanalyse#Absolute Häufigkeit|absolute Häufigkeit]]), der **Modus** $\bar{x}_{D}$ angegeben.
```python
modus = df["Geschlecht"].mode()[0]
```

## [[Statistisches Merkmal|Ordinale Merkmale]]
Die Werte haben eine natürliche Reihenfolge. Wir können aber mit diesen Werten im Allgemeinen nicht rechnen. Wenn wir die Daten aufsteigend der Reihe nach sortieren, können wir das sogenannte $p$ **-Quantil** bestimmen. Das ist ein Wert $x_p$, der die Daten in einen unteren Teil und in einen oberen Teil unterteilt: $p\%$ der Daten sind kleiner oder gleich als $x_p$ und $(1-p)\%$ der Daten sind grösser. Mit $p=50\%$ sind in beiden Teilen ungefähr gleich viele Daten, daher heisst $x_{50\%}$ der **Median**. Der Wert $x_{25\%}$ heisst **unteres Quartil**, weil ungefähr ein Viertel der Daten kleiner als $x_{25\%}$ sind und der Wert $x_{75\%}$ heisst **oberes Quartil**, weil ungefähr drei Viertel der Daten kleiner als $x_{75\%}$ sind.

```python
werte,absH = np.unique(df["Prädikat"],return_counts=True)
# sortieren der Werte nach natürlicher Reihenfolge
werte = np.array([werte[1],werte[2],werte[3],werte[0]])
absH = np.array([absH[1],absH[2],absH[3],absH[0]])
# Häufigkeiten bestimmen
relH = absH/df.shape[0]
relSH = np.array([relH[0],sum(relH[:2]),sum(relH[:3]),sum(relH)])

# Media bestimmen oder 50%-Quantil
median = werte[0]
i = 1
while i <= m:
    if relSH[i] > 0.5:
        break
    median = werte[i]
    i += 1
```


## [[Statistisches Merkmal|Metrische Merkmale]]
Da mit metrischen Werten gerechnet werden kann, lässt sich die Summe aller Daten gleichmässig auf alle statistischen Einheiten verteilen. Dieses **arithmetische Mittel** $\bar{x}$ beschreibt, wie gross die Werte im Mittel sind. Das arithmetische Mittel wird aber von einzelnen Werten stark beeinflusst. 
Der **Median** hingegen wird von extremen Werten weniger beinflusst, weil sehr grosse oder sehr kleine Werte die Reihenfolge in der Mitte nicht verändern.
```python
q50 = df["Alter"].median()
x_bar = df["Alter"].mean()
```