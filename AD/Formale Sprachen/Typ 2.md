Sprach vom Typ 2 sind [[Formale Sprache|formale Sprachen]] und werden als **kontextfreie Sprache** bezeichnet.

Der Typ 2 schreibt folgende Regel vor:
- Die linke Seite der [[Formale Grammatik|Produktion]] dar nicht mehr als **ein Nichtterminalsymboll** sein.

Dadurch ist diese Art der Sprache extrem bedeutsam für die Informatik, insbesondere für die Programmiersprachen.

=> Das Wortproblem ist mit einer [[AD/Algorithmen/Komplexität|Komplexität]] von $O(n^{3})$ lösbar (CKY-Algorithmus). Im Bestcase kann das Problem sogar mit $O(n)$ gelöst werden. ($n$ entspricht der Länge des Wortes.)

## Beispiel
$N = \{s\}$
$T = \{+,*(,),a\}$
$P=\{s\to s+s,s\to s*s,s\to (s),s\to a\}$

Wort:
$s\to s*s\to a*s\to a*a$

=> $G_{2}$ erzeugt Mathematische ausdrücke.
=> Jedes Wort ist mit einen [[Syntaxbaum]] darstellbar.


## Darstellungsarten
- [[Syntaxbaum]]
- [[Syntaxdiagramm]]
- [[EBNF]]


