Der Typ 3 einer [[Formale Sprache|formalen Sprache]] ist schränkt die [[Formale Grammatik|Grammatik]] am meisten ein:
- Auf der linke Seite der Produktion, darf **nur ein Nichtterminalsymbol** stehen. (wie bei [[Typ 2]]).
- Auf der rechten Seite dar entweder **ein Nichtterminal und ein Terminal** oder **nur ein Terminal**-Symbol stehen.
- Wenn das Nichtterminalsymbol immer konsequent rechts steht, nennen man die Sprache **rechtsregulär.**

=> Für Sprachen des Typ 3 ist das [[Wortproblem]] mit einer [[AD/Algorithmen/Komplexität|Komplexität]]
von $O(n)$ lösbar.

## Beispiel
$N=\{s,B\}$
$T=\{0,1\}$
$P=\{s\to 0,s\to 1, B\to0,B\to 1, s\to 1B,B\to 0B,B\to1B\}$
$s$

Diese Sprache definiert binäre Ausdrücke ohne eine führende 0.

## Darstellungsarten
- [[Syntaxbaum]]
- [[Syntaxdiagramm]]
- [[BNF/EBNF]]
- [[Regulärer Ausdruck]]