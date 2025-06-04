Die blosse Betrachtung eines Diagramms ist kein präzises Mittel zu Messung der **statistischen Signifikanz**, daher wird der **p-Wert** benutzt.

>[!Definition]
>Der **$p$-Wert** ist **die Häufigkeit**, mit der das Zufallsmodell ein Ergebnis erzeugt, das **extremeer** ist **als das beobachtete** Ergebnis.

Bevor ein [[Statistischer Test|statistischer Test]] durchgeführt wird, wird ein **Schwellenwert festgelegt**
- *extremer als $5\%$ der Zufallsergebnisse ([[Hypothese#Nullhypothese|Nullhypothese]])*.

Dieser Schwellenwert $\alpha$ wird als **Signifikanzniveau** bezeichnet.

Die entscheidende Frage, welche der p-Wert beantwortet ist:
- **Wie hoch ist die Wahrscheinlichkeit eines so extremen Ergebnisses bei einem gegebenen Zufallsmodell?**

>[!error]
> Ein signifikanter $p$-Wert erbringt keinen _Beweis_. Die logische Grundlage für die Schlussfolgerung **statistisch signifikant** ist schwächer, wenn man die wahre Bedeutung des $p$-Wert versteht.


**ASA-Empfehlungen:**
1. $\pmb{p}\textbf{-Werte}$ können anzeigen, wie unvereinbar die Daten mit einem bestimmten statistischen Modell sind.
2. $\pmb{p}\textbf{-Werte}$ messen nicht die Wahrscheinlichkeit, dass die untersuchte Hypothese wahr ist, oder die Wahrscheinlichkeit, dass die Daten allein durch Zufall entstanden sind.
3. Wissenschaftliche Schlussfolgerungen und geschäftliche oder politische Entscheidungen sollten nicht nur darauf beruhen, ob ein $\pmb{p}\textbf{-Wert}$ einen bestimmten Schwellenwert überschreitet.
4. Ordnungsgemässe Schlussfolgerungen erfordern eine umfassende Berichterstattung und Transparenz.
5. Ein $\pmb{p}\textbf{-Wert}$ oder eine **statistische Signifikanz** ist kein Mass für die Grösse eines Effekts oder die Bedeutung eines Ergebnisses.
6. Ein $\pmb{p}\textbf{-Wert}$ an sich ist kein gutes Mass für die Evidenz eines Modells oder einer Hypothese.

## Fehler Typ 1
Ein **Fehler des Typ 1** ist ein Fehler, bei dem man irrtümlich zum Schluss kommt, dass ein Effekt vorhanden ist, obwohl dieser nur durch Zufall entstanden ist.

## Fehler Typ 2
Ein **Fehler des Typ 2** ist ein Fehler, bei dem man irrtümlich Feststellt, dass der Effekt nur auf Zufall zurückzuführen ist, obwohl er tatsächlich vorhanden ist.

Eigentlich ist _ein Fehler des Typs 2_ weniger ein Fehler als vielmehr die Einschätzung, dass der **Stichprobenumfang zu klein** ist, um den **Effekt zu erkennen**.

## Signifikanzniveau
Das Signifikanzniveau definiert die Schwelle des $p$-Werts, z.B. $5\%$ oder $1\%$.

Liegt ein $p$-Wert unterhalb der statistischen Signifikanz (z.B. über $5\%$) heisst das:
- dass ein Effekt mit dieser Stichprobe nicht nachgewiesen ist. Mit einer grösseren Stichprobe könnte es anders aussehen.

Ziel ist es vor allem **Fehler des Typ 1 zu vermeiden.**

## Berechnung
Angenommen man nutzt einen [[Permutationstest]] um die Differenz der mittleren Verweildauer auf zwei Webseiten zu messen wird der $p-Wert$ wie folgt berechnet:
```python
mu_diff_permutiert = []
# calculate mu_diff_permutiert mit Permutationstest
p_value = 100*(mu_diff_permutiert >= mu_diff_beobachtet).mean()
```
