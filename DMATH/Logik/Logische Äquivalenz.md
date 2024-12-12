>[!Info]
>Die [[Proposition|Propositionen]] $p$ und $q$ heissen **logisch äquivalent**, falls $p\leftrightarrow$ eine [[Tautologie und Kontradiktion|Tautologie]] ist. Man schreibt dann $p \Leftrightarrow q$ oder auch $p\equiv q$.

## Logische Äquivalänzgesetze

| Gesetz                                                       |                                                 | Name                             |
| ------------------------------------------------------------ | ----------------------------------------------- | -------------------------------- |
| $p\land T=p$                                                 | $p\lor F=p$                                     | Identität                        |
| $p\lor T=T$                                                  | $p\land F=F$                                    | Dominaz                          |
| $p\lor p=p$                                                  | $p\land p=p$                                    | Idempotenz                       |
| $\neg(\neg p)=p$                                             |                                                 | Doppelnegation                   |
| $p\lor\neg p=T$                                              | $p\land\neg p=F$                                | [[Tautologie und Kontradiktion]] |
| $p\lor q\equiv q\lor p$                                      | $p\land q\equiv q\land p$                       | Kommutativität                   |
| $p\lor(p\land q)\equiv p$                                    | $p\land(p\lor q)=p$                             | Absorption                       |
| $(p\lor q)\lor r \equiv p\lor(q\lor v)$                      | $(p\land q)\land r \equiv p\land(q\land r)$     | Assoziativgesetzt                |
| $p\lor(q\land r)\equiv(p\lor q)\land(p\lor r)$               | $p\land(q\lor r)\equiv(p\land q)\lor(p\land r)$ | Distributivgesetz                |
| $\neg(p\land q)\equiv\neg p \land \neg q$                    | $\neg(p\lor q)\equiv \neg p \land\neg q$        | De Morgan's Gesetz               |
| $p\to q\equiv\neg p\lor q$                                   |                                                 |                                  |
| $p\to q\equiv\neg q \to\neg p$                               |                                                 |                                  |
| $p\lor q\equiv\neg p\to q$                                   |                                                 |                                  |
| $p\land q\equiv\neg(\neg p\to q)$                            |                                                 |                                  |
| $\neg(p\to q)\equiv p\land\neg q$                            |                                                 |                                  |
| $p\leftrightarrow q\equiv(p\to q)\land(q\to p)$              |                                                 |                                  |
| $p\leftrightarrow \equiv\neg p\leftrightarrow \neg q$        |                                                 |                                  |
| $p\leftrightarrow q\equiv(p\land q)\lor(\neg p \land\neg q)$ |                                                 |                                  |
| $\neg(p\leftrightarrow q)\equiv p\leftrightarrow\neg q$      |                                                 |                                  |
| $(p\to q)\land(p\to r)\equiv p\to(q\land r)$                 |                                                 |                                  |
| $(p\to r)\land(q\to r)\equiv(r\land q)\to r$                 |                                                 |                                  |
| $(p\to q)\lor (p\to r)\equiv p\to(q\lor r)$                  |                                                 |                                  |
| $(p\to r)\lor(q\to r)\equiv(r\land q)\to r$                  |                                                 |                                  |
| $p\oplus q\equiv(p\lor q)\land(\neg p \lor\neg q)$           |                                                 |                                  |
| $\neg(p\oplus q)\equiv(p\land q)\lor(\neg p\lor\neg q)$      |                                                 |                                  |
| $\neg(p\oplus q)\equiv p\leftrightarrow q$                   |                                                 |                                  |

## Beispiel
### Beispiel 1
Zeige dass $p\lor(q\land r)\equiv(p\lor q)\land(p\lor r)$
#### Variante Wahrheitstabelle

| $p$ | $q$ | $r$ | $q\land r$ | $p\lor(p\land r)$ | $p\lor q$ | $p\lor r$ | $(p\lor q)\land(p\lor r)$ |
| --- | --- | --- | ---------- | ----------------- | --------- | --------- | ------------------------- |
| 0   | 0   | 0   | 0          | **0**             | 0         | 0         | **0**                     |
| 0   | 0   | 1   | 0          | **0**             | 0         | 1         | **0**                     |
| 0   | 1   | 0   | 0          | **0**             | 1         | 0         | **0**                     |
| 0   | 1   | 1   | 1          | **1**             | 1         | 1         | **1**                     |
| 1   | 0   | 0   | 0          | **1**             | 1         | 1         | **1**                     |
| 1   | 0   | 1   | 0          | **1**             | 1         | 1         | **1**                     |
| 1   | 1   | 0   | 0          | **1**             | 1         | 1         | **1**                     |
| 1   | 1   | 1   | 1          | **1**             | 1         | 1         | **1**                     |
#### Variante Analytik
$$
\begin{align}
p\lor(q\land r)&\equiv(p\lor q)\land(p\lor r) \\
&\equiv p\lor(q\land r)
\end{align}
$$
### Beispiel 2
Zeige dass $p\lor(p\land q)\equiv p$
$$
\begin{align}
p\lor(p\land q)&\equiv q \\
&\equiv(p\land T)\lor(p\land q) \\
&\equiv p \land(T\lor q) \\
&\equiv p\land T \\
&\equiv p
\end{align}
$$
### Beispiel 3
Zeige dass $(p\lor\neg(q\land p))\land(r\lor(s\lor r))\equiv r\lor s$ ist.
$$
\begin{align}
r\lor s&\equiv(p\lor\neg(q\land p))\land(r\lor(s\lor r)) \\
&\equiv (p\lor(\neg q \lor \neg p)) \lor(r\lor(s\lor r)) \\
&=(p\lor\neg q \lor \neg p) \lor(r\lor(s\lor r)) \\
&=(p\lor\neg p\lor\neg q) \lor(r\lor(s\lor r)) \\
&=(T\lor\neg q) \lor(r\lor(s\lor r)) \\
&=(T) \lor(r\lor s\lor r) \\
&=(T) \lor(r\lor r\lor s) \\
&=T \lor r\lor r\lor s \\
&=T \lor r\lor s \\
&= r\lor s
\end{align}
$$
