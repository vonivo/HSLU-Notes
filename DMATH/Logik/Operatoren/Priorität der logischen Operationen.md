In einem logischen Ausdruck wird der Operator mit der **höchsten Priorität** mit seinen Operanden **zuerst zusammengefasst** (Höchste Prio =>1). Gibt es mehrere Operatoren mit denselben Prioritäten erfolgt die Auswertung von links nach rechts.

| Operator          | Priorität |
| ----------------- | --------- |
| $\neg$            | 1         |
| $\land$           | 2         |
| $\lor$            | 2         |
| $\leftrightarrow$ | 3         |
| $\to$             | 3         |
Also:
- [[Implikation (Subjunktion)|Implikation]] und [[Bikonditional (Bijunktion)|Bikonditional]] als erstes
- [[DMATH/Logik/Operatoren/Konjunktion]] und [[Disjunktion]] als zweites
- [[Negation]] am Schluss