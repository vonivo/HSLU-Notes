---
aliases:
  - Bikonditional
---
>[!Info]
>Das **Bikonditional** $p \leftrightarrow q$ (gelesen $p$ genau dann, wenn $q$) ist diejenige [[Proposition]], die wahr ist, wenn $p$ und $q$ **die selben Wahrheitswerte** haben.


## Wahrheitstabelle
Die bikonditionale [[Proposition]] ist eine [[Konjunktion]] von zwei [[Implikation (Subjunktion)|Implikationen]] oder der [[Negation|negation]] von einem [[XOR]]

| $p$ | $q$ | $p\to q$ | $q\to p$ | $(p\to q) \land(q\to p)$ | $p\leftrightarrow q$ | $p\oplus q$ | $\neg (p\oplus q)$ |
| --- | --- | -------- | -------- | ------------------------ | -------------------- | ----------- | ------------------ |
| 0   | 0   | 1        | 1        | 1                        | 1                    | 0           | 1                  |
| 0   | 1   | 1        | 0        | 0                        | 0                    | 1           | 0                  |
| 1   | 0   | 0        | 1        | 0                        | 0                    | 1           | 0                  |
| 1   | 1   | 1        | 1        | 1                        | 1                    | 0           | 1                  |
## Beispiel
Die Konjunktionen der Propositionen:
$$
\begin{align}
p &= \text{"Sie können das Flugzeug nehmen"} \\
q &= \text{"Sie kaufen sich ein Ticket"}
\end{align}
$$
ist
$$
p\leftrightarrow  q=\text{"Sie können den Flug nehmen wenn sie sich ein Ticketkaufen (oder umgekehrt)"}
$$


