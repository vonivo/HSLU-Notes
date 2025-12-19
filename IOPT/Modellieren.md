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

#### Implementation des [[BeschreibendesModell]]
![[BeschreibendesModell.png]]

#### Zulässige Alternativen
Nicht alle Kombinationen an Entscheidungsvariablen sind erlaubt, da die Materialien limitiert sind. Daher werden Bedingungen eingeführt.

**Beispiel nicht zulässige Variable**
![[UnzulässigeVariable.png]]

**Mathematische Beschreibung**
![[MathematischesBeschreibendesModell.png]]

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

## Beispiel 3