Die [[Kovarianz]] $\sigma_{ab}$ und der darauf basierende [[Kovarianz#Korrelationskoeffizient|Korrelationskoeffizient]] [[Statistisches Merkmal|metrische Merkmale]] voraussetzt, existiert der **Rangkorrelationskoeffizient** um mit [[Statistisches Merkmal|ordinalen Merkmalen]] zu rechnen.

Wenn mindestens ein Merkmal nur ordinal ist, wird der **Rangkorreklationskoeffizient nach Spearman** verwendet.
In diesem Fall werden die Werte $a_{1},a_{2},\dots,a_{n}$ und $b_{1},b_{2},\dots,b_{n}$ sogenannte **Rangzahlen** zugewiesen:
$$
R(a_{i}) \text{ und } R(b_{i})
$$
- der kleinste $a_{i}$- bzw. $b_{i}$-Wert erhält die **Rangzahl 1**,
- zweitkleinste $a_{i}$- bzw. $b_{i}$-Wert erhält die **Rangzahl 2**,
- usw.
- der grösste $a_{i}$- bzw. $a_{i}$-Wert erhält die **Rangzahl** $n$

Wenn mehrere Werte eines Merkmals gleich gross sind (man spricht von **Bindungen**), erhalten diese alle **als Rangzahl das arithmetische Mittel** der betreffenden Rangzahlen.

**Beispiel**
Die Prädikate: ungenügend, genügend, mässig, gut, sehr gut
Da "mässig" und "genügend" die gleich gross sind gibt es diese Rangzahlen

| Prädikat  | Rangzahl |
| --------- | -------- |
| ungeügend | 1        |
| genügend  | 2        |
| mässig    | 3        |
| gut       | 4        |
| sehr gut  | 5        |
Nu wird das Arithmethische Mittel genutzt: $$
\frac{1}{2}(3+2) = 2.5
$$
Daraus folgt diese Tabelle:

| Prädikat  | Rangzahl |
| --------- | -------- |
| ungeügend | 1        |
| genügend  | 2.5      |
| mässig    | 2.5      |
| gut       | 4        |
| sehr gut  | 5        |
Der **Rangkorrelationskoeffizient** erhält man nun einfach, indem man den Korrelationskoeffizienten nach Bravais/Pearson auf die Rangzahlen anwendet:
$$
r_{Sp}=\frac{\sigma_{R(a)R(b)}}{\sigma_{R(a)}\cdot \sigma_{R(b)}}
$$
