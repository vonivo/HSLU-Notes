[[Lagemass]] und [[Streumass]] fassen die Daten mit einem typischen Wert zusammen.
Es ist jedoch auch wichtig, die **gesamte Verteilung** der Daten zu untersuchen.

## [[Statistisches Merkmal|Nominale Merkmale]]
Die Verteilung von [[Statistisches Merkmal|nominalen Merkmalen]] wird häufig in einem **Kreisdiagramm** dargestellt. Die [[Häufigkeitsanalyse#Relative Häufigkeit|relative Häufigkeiten]] aller Werte des [[Statistisches Merkmal|Merkmals]] werden proportional als Kreissektor abgebildet.
```python
import matplotlib.pyplot as plt

werte,absH = np.unique(df["Geschlecht"],return_counts=True)
plt.pie(absH,labels=werte,startangle=90,autopct="%1.1f%%")
plt.show()
```

## [[Statistisches Merkmal|Ordinale Merkmale]]
Für ordinale Merkmale ist ein **Balkendiagramm** besser geeignet, weil die natürliche Reihenfolge der Werte von links nach rechts dargestellt werden kann. Die [[Häufigkeitsanalyse#Absolute Häufigkeit|absoluten]] oder [[Häufigkeitsanalyse#Relative Häufigkeit|relative Häufigkeiten]] der Werte werden proportional zur Höhe eines Balkens abgebildet.
```python
import seaborn as sns
sns.countplot(data=df,x="Prädikat",
              order=["genügend","gut","sehr gut","ausgezeichnet"])
```

## [[Statistisches Merkmal|Metrische Merkmale]]
Die Abstände zwischen Werten eines _metrischen Merkmales_ sind hingegen eindeutig gegeben. Oft haben metrische Merkmale auch viele verschiedene Werte, so dass ein Balkendiagramm die Charakteristik einer Verteilung nicht mehr sinnvoll abbildet. Daher unterteilen wir die Werte eines metrischen Merkmals in Abschitte, sogenannte **Klassen**, und bilden die absoluten oder relativen Häufigkeiten der Werte in diesen Klassen mit Rechtecken ab, deren Höhe proportional zu diesen Häufigkeiten ist. Wenn also Häufigkeiten über einer Unterteilung der Zahlenachse abgebildet werden, entsteht ein **Histogramm**.

### Histogramm
```python
fig = plt.figure(figsize=(10,3))
ax1 = fig.add_subplot(1,2,1)
ax1 = sns.histplot(data=df,x="Alter",bins=2)
ax2 = fig.add_subplot(1,2,2)
ax2 = sns.histplot(data=df,x="Alter",bins=30)
plt.show()
```
![[Histogramm.png]]
### Dichtediagramm
In Histogrammen werden die absoluten Häufigkeiten der Klassen proportional zur Höhe der Rechtecke abgebildet. In **Dichtediagrammen** werden die relativen Häufigkeiten der Klassen proportional zur Fläche der Rechtecke abgebildet:
```python
fig = plt.figure(figsize=(10,3))
ax1 = fig.add_subplot(1,2,1)
ax1 = sns.histplot(data=df,x="Alter",bins=2,stat="density")
ax2 = fig.add_subplot(1,2,2)
klassen = np.arange(23,70)
ax2 = sns.histplot(data=df,x="Alter",bins=klassen,stat="density")
plt.show()
```
![[density_plot.png]]Ein Histogramm oder Dichtediagramm heisst:
- **symmetrisch**, wenn die meisten Daten um den Mittelwert leigen und ungefähr die Hälfte der daten unter bzw. über dieser mittleren Lage sind.
- **linksschief**, wenn die Daten weiter nach links abfallen. Es gibt also auf der linken Seite extreme Werte.
- **rechtsschief**, wenn die Daten weiter nach rechts abfallen. Es gibt auf der rechten Seite extreme Werte.

### Boxplot
Um die Lage der Daten und die Symmetrie eines metrischen Merkmals graphsich darzustellen, können wir einen sogenannten **Blox-Plot** zeichen:
- mit einem Rechteck, dessen Höhe dem Quartilsabstand $Q$ entspricht.
- der Median $x_{50}$ unterteil das Rechteck in zwei Teile.
- unten und oben wird mit einem _Whisker_ der kleinste beziehungsweise der grösste noch normale Wert angegeben. Wert, die $1.5\cdot Q$-mal weiter vom unteren beziehungsweise vom oberen Quartil entfernt sind, heissen **Ausreisser** und sind nicht mehr innerhalb der beiden Whisker. Solche extremen Werte werden im Box-Plot mit einzelnen Punkten abgebildet.
```python
import seaborn as sns
fig, ax = plt.subplots()
ax = sns.boxplot(y="Alter",data=df,width=0.15,
                 color="0.7",flierprops={"marker":"x"})
```
![[boxplot.png]]