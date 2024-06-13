Der Typ 1 ist eine Art der [[Formale Sprache|formalen Sprach]] welche auch **nicht verkürzende Sprache** genannt wird.

Daher gelten folgende Regeln:
- Die rechte Seite der [[Formale Grammatik|Produktion]] darf nicht kürzer sein als die linke Seite.

=> Daher ist diese Sprache **längenmonotn** da sukzessive immer längere Worte entstehen.

=> Das Wortproblem ist für dieses Typ lösbar, der [[AD/Algorithmen/Komplexität|Aufwand]] dafür kann jedoch astronomisch hoch sein.

## Beispiel
$N = \{s,A,B\}$
$T = \{a,b,c\}$
$P = \{s\to abc, s\to aAbc, Ab\to bA,Ac\to Bbcc,bB \to Bb,aB \to aaA,ab\to aa\}$
$s$

Mit dieser Sprache lässt sich folgendes Wort erzeugen:
$s\to aAbc\to abAc\to abBbcc\to aBbbcc\to aabbcc$

Also $G_{1}$ erzeugt also hintereinander $n$-Mal die Symbole $a,b,c$.
