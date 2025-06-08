Bei einer **multiplen linearen Regression** werden mehre Einflussgrössen Prädiktoren in einem linearen Modell gleichzeitig betrachtet:
$$
y=predict(x_{1},x_{2},\dots,x_{n})=a_{1}\cdot x_{1}+a_{2}\cdot x_{2}+\dots+a_{n}\cdot x_{n}+b
$$

## Vorwärtselektion
Beim "fitting" eines Modells...

- Heissen _mehr Prädikatoren_ nicht, dass das entstandene Modell dadurch besser wird.
- Sollten wir deshalb sparsam mit dem Verwenden von Prädikatoren umgehen.
- Sollten wir bei gleichen Aspekten das einfachere Modell vorziehen.
>[!Definition]
>Bei der Vorwärtsselektion beginnen wir mit dem _einfachsten Modell_ und fügen schrittweise weitere *Prädikatoren* hinzu. Dabei suchen wir jeweils denjenigen Prädikator, durch dessen hinzufügen das Modell die grösste Optimierung erfahren hat.
Sobald eine Verbesserung nicht mehr deutlich erkennbar ist, wird mit der Erweiterung des Modells gestoppt.

**Vorgehen**
1. Füge einem Modell nacheinander jeden übrigbleibenden _Prädiktor_ hinzu.
2. Berechne für jedes Modell den $AIC$ ($n$ = Anzahl Daten in der Stichprobe)
$$
2\cdot \text{Anzhal der Parameter im Model} + n \cdot \log\left( \frac{RSS}{n} \right)
$$
3. Wähle den Prädiktor aus, dessen Hinzunahme den AIC am stärksten senkt. Wenn kein Prädiktor den AIC senkt, stoppe
4. Beginne erneut von Vorne