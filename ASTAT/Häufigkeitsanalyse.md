>[!info]
>Die grundlegendste Aufbereitung statistischer Daten ist die Darstellung, wie häufig die Ausprägungen eines Merkmals vorkommen.

## Absolute Häufigkeit
Die absolute Häufigkeit $n(x)$ ist die Anzahl, wie oft ein Wert $x$ vorkommt.

## Relative Häufigkeit
Die relative Häufigkeit $h(x) = \frac{n(x)}{n}$ ist der Anteil, mit dem ein Wert $x$ vorkommt.


## Summenhäufigkeit

Weil [[Statistisches Merkmal|ordinale]] und [[Statistisches Merkmal|metrische Merkmale]] eine Reihenfolge haben, können wir die Häufigkeit auch der Reihe nach kumulieren.
### Absolute Summenhäufigkeit
Die absolute Summenhäufigkeit $N(x)$ ist die Anzahl wie oft ein Wert kleiner oder gleich $x$ vorkommt.

### Relative Summenhäufigkeit
Die relative Summenhäufigkeit $H(x)=\frac{N(x)}{n}$ ist der Anteil mit dem Werte kleiner oder gleich $x$ vorkommen.

## Empirische Häufigkeitsverteilung
Die Auflistung aller Werte $x_1, x_2, \ldots, x_m$ eines Merkmals zusammen mit ihren Häufigkeiten nennen wir eine **empirische Häufigkeitsverteilung**

>[!warning]
>Aus der empirischen Häufigkeitsverteilung können wir nicht mehr herauslesen, was für einen Wert eine statistische Einheit bei einem Merkmal hat. Wir sehen nur noch, wie oft oder wie häufig die Werte eines Merkmals vorkommen. **Es geht Information verloren!** 

## Beispiel
$$
\begin{bmatrix}
Anna & w & \text{ausgezeichnet} & 27 \\ 
Beat & m & \text{gut} & 34 \\ 
Cary & w & \text{sehr gut} & 27 \\ 
Dana & w & \text{sehr gut} & 27 \\ 
Elif & w & \text{gut} & 27  \\
Faro & w & \text{ausgezeichnet} & 27  \\
Gabi & w & \text{sehr gut} & 27  \\
Hans & w & \text{genügend} & 27  \\
Ivea & w & \text{sehr gut} & 27 \\ 
Jose & w & \text{gut} & 27 \\
\end{bmatrix}
$$
```python
namen = ["Anna","Beat","Cary","Dana","Elif","Faro","Gabi","Hans","Ivea","Jose"]
geschlecht = ["w","m","m","w","w","m","w","m","w","w"]
prädikat = ["ausgezeichnet","gut","sehr gut","sehr gut","gut","ausgezeichnet","sehr gut","genügend","sehr gut","gut"]
alter = [27,34,29,24,25,27,27,69,26,31]

import pandas as pd
df = pd.DataFrame({"Name":namen,"Geschlecht":geschlecht,"Prädikat":prädikat,"Alter":alter})

```

### Empirische Verteilung Geschlecht
```python
import numpy as np

dim = df.shape
(werte,absH) = np.unique(df["Geschlecht"],return_counts=True)

for i in range(len(werte)):
    print("n(" + werte[i] + ") =",absH[i])

for i in range(len(werte)):
    print("h(" + werte[i] + ") =",absH[i]/dim[0])
```
```
n(m) = 4
n(w) = 6
h(m) = 0.4
h(w) = 0.6
```
