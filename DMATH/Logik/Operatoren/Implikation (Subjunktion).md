---
aliases:
  - Implikation
---
>[!Info]
>die **Implikation** $p\to q$ (gelesen $p$ impliziert $q$ oder falls $p$ dann $q$) ist die jeneige [[Proposition]], die genau dann **falsch** ist wenn $p$ **wahr** und $q$ **falsch** ist.

Die Implikation $p\to q$ ist nur dann falsch, wenn die Hypothese $p$ wahr ist und die Konklusion $q$ falsch.
## Wahrheitstabelle

| $p$ | $q$ | $p\to q$ |
| --- | --- | -------- |
| 0   | 0   | 1        |
| 0   | 1   | 1        |
| 1   | 0   | 0        |
| 1   | 1   | 1        |

## Beispiel
Aussagen:
$$
\begin{align}
p&=\text{"ich werde gewählt"} \\
q&=\text{"ich senke die Steuern"}
\end{align}
$$
Mit der Implikation $p\to q$ wird wie folgt formuliert **"Wenn ich gewählt werden, senke ich die Steuern"**

| Politiker wird gewählt | Politiker senkt die Steuern | Versprechen gehalten |
| ---------------------- | --------------------------- | -------------------- |
| $p$                    | $q$                         | $p\to q$             |
| 0                      | 0                           | 1                    |
| 0                      | 1                           | 1                    |
| 1                      | 0                           | 0                    |
| 1                      | 1                           | 1                    |

=> Sobald $p$ wahr ist, muss $q$ auch wahr sein.