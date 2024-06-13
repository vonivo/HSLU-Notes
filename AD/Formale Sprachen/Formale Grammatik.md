> [!info]
> Die **formale Grammatik** ist die formale Definition einer Sprache.

Ein formale Grammatik $G$ ist der 4-Tupel $G = (N,T,P,s)$
- $N$ -> Menge aller [[Formale Sprache#Elemente|Nichtterminalsymbolen]]
- $T$ -> Menge aller [[Formale Sprache#Elemente|Terminalsymbolen]]
- $P$ -> Menge von Produzenten
- $s$ -> Startsymbol ($s \in N$ gehört immer dazu.)

## Beispiel
$N = \{s,B\}$
$T = \{0,1\}$
$P = \{s\to 0, s\to 1,s \to1B, B\to 0B,B\to1B,B\to 1,B\to 0\}$
$s$

Durch die Produktion $P$ lässt sich genau bestimmen, welche Wörter zur Sprache gehören:

$s\to1B\to10B\to101B\to1010$

### Anmerkungen
- Mit den Produktionen lassen sich sukzessive Wörter bilden: "linkeSeite -> rechteSeite".
- Auf der Linkenseite muss **mindestens ein Nichtterminalsymbol** stehen. Terminalsymbole haben terminiert.
