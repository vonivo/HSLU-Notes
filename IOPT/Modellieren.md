### Beispiel 1
#### Problem
>[!Error]
>Ein Bootfabrikant stellt zwei Boottypen her:
>- Segelbote
>- Motorbote

Deckungsbeiträge (pro Stk.):
- Motorboote -> 2400
- Segelboot -> 2000

Momentan knapp verfügbare Materialien:
- Segeltuch (nur von Segelbooten gebraucht)
- Mototren (nur duch Motorboot gebraucht)
- Glasfaser (von beiden Boottypen gebraucht)

**Wie viele Einheiten soll der Hersteller von jedem Typ herstellen**

#### Daten

|                 | Segelboot | Motorboot |
| --------------- | --------- | --------- |
| Deckungsbeitrag | 2400      | 2000      |

| Material  | Bedarf Segelboot | Bedarf Motorboot |
| --------- | ---------------- | ---------------- |
| Segeltuch | 4                | 0                |
| Motoren   | 0                | 1                |
| Glasfaser | 8                | 4                |

| Material  | Verfügbare Menge |
| --------- | ---------------- |
| Segeltuch | 400              |
| Motoren   | 120              |
| Glasfaser | 1000             |

#### [[Einflussdiagramm]]
**Variante 1**

![[Einflussdiagramm_v1.png]]
**Variante 2**
![[Entscheidungsdiagramm_v2.png]]**Spezifikation der Bezeichnungen**
$$
\begin{align}
k_{d} &= d_{s} \times x_{s} + d_{m} \times x_{m} \\
k_{s} &= b_{s,s} \times x_{s} \\
k_{m} & = b_{m,m} \times x_{m} \\
k_{g} & = b_{g,s} \times x_{s} + b_{g,m} \times x_{m}
\end{align}
$$

#### Implementation des [[Beschreibendes Modell]]
![[BeschreibendesModell.png]]

#### Zulässige Alternativen
Nicht alle Kombinationen an Entscheidungsvariablen sind erlaubt, da die Materialien limitiert sind. Daher werden Bedingungen eingeführt.

**Beispiel nicht zulässige Variable**
![[UnzulässigeVariable.png]]

**Mathematische Beschreibung**
![[MathematischesBeschreibendesModell.png]]

#### [[Optimierungsmodelle|Optimierungsmodell]]
Maximiere $k_{1}$ unter den Bedingungen:
$$
\begin{align}
k_{1}-2400x_{1}-2000x_{2} &= 0 \\
k_{2}-4x_{1} & =0 \\
k_{3}-1x_{2} & =0 \\
k_{4}-8x_{1}-4x_{2} & =0 \\
k_{2} &\leq 400 \\
k_{3} &\leq 120 \\
k_{4} & \leq 1000 \\
x_{1} & \geq 0,x_{2}\geq 0
\end{align}
$$
oder
maximiere $2400x_{1} + 2000x_{2}$ unter den Bedingungen:
$$
\begin{align}
4x_{1} & \leq 400 \\
x_{2} & \leq 120 \\
8x_{1}+4x_{2} & \leq 1000 \\
x_{1}\geq 0, x_{2} & \geq 0
\end{align}
$$
## Beispiel 2
Ein Busunternehmen führt Tagesausflüge aus. Aufgrund seines Angebots werden folgende Bedarfe an Buschauffeuren für die verschiedenen Wochentage ermittelt:

| Mo  | Di  | Mi  | Do  | Fr  | Sa  | So  |
| --- | --- | --- | --- | --- | --- | --- |
| 14  | 12  | 18  | 16  | 15  | 16  | 19  |

Die Chauffeure arbeiten gemäss Dienstplänen, die folgende Bedingung erfüllen müssen: Ein Chauffeur ist 5 Tage aufeinander im Einsatz und hat dann 2 Ruhetage.

**Wie viele Chauffeure braucht es insgesamt, und wie werden sie eingesetzt?**

**Dienstpläne**

|     | Mo  | Di  | Mi  | Do  | Fr  | Sa  | So  |
| --- | --- | --- | --- | --- | --- | --- | --- |
| D1  | 1   | 1   | 1   | 1   | 1   | 0   | 0   |
| D2  | 0   | 1   | 1   | 1   | 1   | 1   | 0   |
| D3  | 0   | 0   | 1   | 1   | 1   | 1   | 1   |
| D4  | 1   | 0   | 0   | 1   | 1   | 1   | 1   |
| D5  | 1   | 1   | 0   | 0   | 1   | 1   | 1   |
| D6  | 1   | 1   | 1   | 0   | 0   | 1   | 1   |
| D7  | 1   | 1   | 1   | 1   | 0   | 0   | 1   |
**Einflussdiagramm**
![[BusEinflussDiagramm.png]]

**Beschreibendes Modell**
$$
\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4} \\
x_{5} \\
x_{6} \\
x_{7}
\end{pmatrix} \to \begin{align}
k_{1}  & = a_{1,1}\times x_{1} + a_{1,2}\times x_{2} + \dots + a_{1,7}\times x_{7} \\
k_{2}  & = a_{2,1}\times x_{1} + a_{2,2}\times x_{2} + \dots + a_{2,7}\times x_{7} \\
k_{3}  & = a_{3,1}\times x_{1} + a_{3,2}\times x_{2} + \dots + a_{3,7}\times x_{7} \\
k_{4}  & = a_{4,1}\times x_{1} + a_{4,2}\times x_{2} + \dots + a_{4,7}\times x_{7} \\
k_{5}  & = a_{5,1}\times x_{1} + a_{5,2}\times x_{2} + \dots + a_{5,7}\times x_{7} \\
k_{6}  & = a_{6,1}\times x_{1} + a_{6,2}\times x_{2} + \dots + a_{6,7}\times x_{7}  \\
k_{7}  & = a_{7,1}\times x_{1} + a_{7,2}\times x_{2} + \dots + a_{7,7}\times x_{7} 
\end{align} \to \begin{pmatrix}
k_{1} \\
k_{2} \\
k_{3} \\
k_{4} \\
k_{5} \\
k_{6} \\
k_{7}
\end{pmatrix}
$$
Wobei:
$$
\begin{align}
k_{1} & \geq 14 \\
k_{2} & \geq 12 \\
k_{3} & \geq 18 \\
k_{4} & \geq 16 \\
k_{5} & \geq 15 \\
k_{6} & \geq 16 \\
k_{7} & \geq 19
\end{align}
$$
![[BusExcel.png]]
#### Optimierungsmodell
minimiere $\sum_{i=1}^{7}x_{i}$ unter den Bedingungen
$$
\begin{align}
x_{1}+x_{4}+x_{5}+x_{6}+x_{7} & \geq 14 \\
x_{1}+x_{2}+x_{5}+x_{6}+x_{7} & \geq 12 \\
x_{1}+x_{2}+x_{3}+x_{6}+x_{7} & \geq 18 \\
x_{1}+x_{2}+x_{3}+x_{4}+x_{7} & \geq 16 \\
x_{1}+x_{2}+x_{3}+x_{4}+x_{5} & \geq 15 \\
x_{2}+x_{3}+x_{4}+x_{5}+x_{6} & \geq 16 \\
x_{3}+x_{4}+x_{5}+x_{6}+x_{7} & \geq 19 \\
x_{j}\geq 0, j=1,2,\dots,7
\end{align}
$$

## Beispiel 3
Ja/Nein-Entscheidungen
- Ob man eine Handlung wählt oder nicht.

Ein Getränkeproduzent beabsichtigt, Abfüllanlagen an neuen Standorten zu
eröffnen, um drei neue Marktregionen M1, M2, M3 zu bedienen.

| Standort | Kapazität | Fixe Betriebskosten |
| -------- | --------- | ------------------- |
| S1       | 20        | 150                 |
| S2       | 20        | 200                 |
| S3       | 10        | 100                 |
| S4       | 10        | 150                 |
**Produktions- und Verteil-Kosten**

| Standort | M1  | M2  | M3  |
| -------- | --- | --- | --- |
| S1       | 20  | 40  | 60  |
| S2       | 30  | 10  | 50  |
| S3       | 30  | 20  | 10  |
| S4       | 10  | 10  | 20  |
**Nachfrage pro Marktregion**

| Nachfrage |     |
| --------- | --- |
| M1        | 10  |
| M2        | 15  |
| M3        | 10  |

**=> Problem**: Welcher Standort wird gewählt und wie wird das Produkt verteilt um die Gesamtkosten möglichst kleinzuhalten.

**Einflussdiagramm**
![[EinflussDiagrammMarktRegionen.png]]

**Beschreibendes Modell**
- $y_{i}$: 1, falls Standort $i$ eröffnet wird
- $x_{i,j}$: Menge, welche von Standort $i$ nach Marktregion $j$ versandt wird.

Konsequenzen:
$$
\begin{align}
k_{1} =& 150y_{1} + 200y_{2}+100y_{3}+150y_{4}\\
 &+ 20x_{1,1} + 40x_{1,2} +60x_{1,3}  \\
 &+ 30x_{2,1} + 10x_{2,2} + 50x_{2,3} \\
 &+ 30x_{3,1} + 20x_{3,2} + 10x_{3,3} \\
 &+ 10x_{4,1} + 10x_{4,2} + 20x_{4,3} 
\end{align}
$$
Bedingungen:
- Kapazität übersteigt Standort Kapa nicht
$$
\begin{align}
k_{2} &= x_{1,1} + x_{1,2} +x_{1,3}  & \geq 20 \\
k_{3} &= x_{2,1} + x_{2,2} +x_{2,3}  & \geq 20 \\
k_{4} &= x_{3,1} + x_{3,2} +x_{3,3}  & \geq 10 \\
k_{5} &= x_{4,1} + x_{4,2} +x_{4,3}  & \geq 10
 \end{align}
$$
- Kapa Marktregion <= Gesendet
$$
\begin{align}
k_{6} & = x_{1,1} + x_{2,1}+x_{3,1}+x_{4,1}  & \geq 10 \\
k_{7} & = x_{1,2} + x_{2,2}+x_{3,2}+x_{4,2}  & \geq 15 \\
k_{8} & = x_{1,3} + x_{2,3}+x_{3,3}+x_{4,3}  & \geq 10
\end{align}
$$
**Implementation im Tabellenkalulator**
![[StandortWahlExcel.png]]

#### Optimierungsmodell
Minimiere:
$$
\begin{align}
&150y_{1} + 200y_{2}+100y_{3}+150y_{4}\\
 &+ 20x_{1,1} + 40x_{1,2} +60x_{1,3}  \\
 &+ 30x_{2,1} + 10x_{2,2} + 50x_{2,3} \\
 &+ 30x_{3,1} + 20x_{3,2} + 10x_{3,3} \\
 &+ 10x_{4,1} + 10x_{4,2} + 20x_{4,3} 
\end{align}
$$
unter den Bedingugnen:
$$
\begin{align}
x_{1,1} + x_{1,2} +x_{1,3}  & \geq 20y_{1} \\
x_{2,1} + x_{2,2} +x_{2,3}  & \geq 20y_{2} \\
x_{3,1} + x_{3,2} +x_{3,3}  & \geq 10y_{3} \\
x_{4,1} + x_{4,2} +x_{4,3}  & \geq 10y_{4} \\
x_{1,1} + x_{2,1}+x_{3,1}+x_{4,1}  & \geq 10 \\
x_{1,2} + x_{2,2}+x_{3,2}+x_{4,2}  & \geq 15 \\
x_{1,3} + x_{2,3}+x_{3,3}+x_{4,3}  & \geq 10 \\
y_{i} \in \{0,1\}, x_{i,j} \geq 0
\end{align}
$$
