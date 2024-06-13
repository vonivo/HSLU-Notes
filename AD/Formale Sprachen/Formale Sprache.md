Eine Sprache ist definiert durch **Syntax** (Grammatik) und **Semantik** (Bedeutung/Logik/Inhalt).

Bei einer formalen Sprache sind **Syntax** und **Semantik** so klar definiert, **keine Fehlinterpretation** mehr möglich ist.

Die Syntax wird meistens **formal definiert** und für die Definition der Semantik wird auf die **natürliche Sprache** zurückgegriffen.

## Elemente
Eine formale Sprache besteht aus:
- Einem **Alphabet** -> (Menge aller Symbolen/Terminalsymbole).
- **Kleensche Hülle $A^{*}$** -> Menge aller Symbolkombinationen.
- Wort $w \in A^{*}$, $\epsilon$ steht für das leere Wort.
- Sprache $L \subseteq A^{*}$ 

### Beispiel
$A =\{0,1\}$
$A* = \{\epsilon,0,1,01,10,101,001, \dots\}$
$L = \{0,01,10,11,100,101,110,111,\dots\}$ -> L ist liste aller Wörter (in userem Fall sind nur Binäre Wörter zulässig.)

=> Sprachen enthalten eine unendliche Anzahl an Wörter. Es braucht einen Mechanismus, welcher beschreibt, wie **zulässige Wörter** gebildet werden können. => [[Formale Grammatik]]

## Unterteilung nach Chomsky
Chomsky definiert vier verschiedene Einschränkung an die [[Formale Grammatik|fromale Grammatik]] einer Sprache, anhand diese sich in vier Typen unterteilten lassen:
- [[Typ 0 ]]-> Rekursiv aufzählbare Sprachen (keine Einschränkung)*
- [[Typ 1]] -> Nichtverkürzende Grammatik **
- [[Typ 2]] -> Kontextfrei Grammatik/Sprache
- [[Typ 3]] -> reguläre Grammatik/Sprache

\* wird auch als Turing-erkennbare Sprache bezeichnet
\** wird auch als Kontextsensitive Sprache bezeichnet.

Dabei gilt:
$T_{3} \subset T_{2} \subset T_{1}\subset T_{0}$

![[Chomsky.png]]

Je eingeschränkter die Grammatik der Sprache, desto einfacher wird das [[Wortproblem]].

Im Gegenzug wird mit zunehmenden grammatischen Regeln die Ausdrucksstärke der Sprache schwächer.

