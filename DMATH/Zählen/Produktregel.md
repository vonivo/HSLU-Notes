> [!Theorem]
> Falls ein erster Ereignis aus $n_{1}$ Möglichkeiten und danach eine zweites (**unabhängig vom ersten Ereignis**) aus $n_{2}$ ausgewählt werden kann, dann gibt es insgesamt $n =n_{1}\cdot n_{2}$ Möglichkeiten, die beiden Ergeignisse zu wählen.

## Beispiel
Wie viele Nummernschilder lassen sich herstellen, wenn jedes Schild aus einer Folge von drei Buchstaben und drei Ziffern besteht.
=> Also zuerst 3 Buchstaben und danach 3 Ziffern.

1. Der Buchstabe kann aus $26$ verschiedenen Buchstaben ausgewählt werden, dass gilt für jeden Buchstaben -> $26\cdot26\cdot26 = 26^{3}$
2. Jede Ziffer kann aus $10$ Verschiedenen ausgewählt werden -> $10\cdot 10 \cdot 10 = 10^{3}$
Diese beiden Ereignisse sind unabhängig also gilt:
$$
\text{\#Anzahl Möglichkeiten} = 26^{3} \cdot 10^{3} = 17'576'000
$$
### Kartesisches Produkt
Für die Anzahl des [[DMATH/Mengen/Kreuzprodukt|kartesischen Produkts]] kann auch die Produktregel verwendet werden:
$$
|A_{1}\times A_{2}\times A_{3}\times\dots \times A_{n}| = |A_{1}|\times |A_{2}|\times |A_{3}|\times\dots\times |A_{n}|
$$
### Beispiel
Wir lösen die vorherige Aufgabe nun mit dem kartesischen Produkt:
Wir definieren:
$$
A_{1} = A_{2}=A_{3}=\{ A,B,\mathbf{C}\dots,Y,Z \}; A_{4}=A_{5}=A_{6}=\{ 0,1,2,\dots,9 \}
$$
Dann hat man:
$$
|A_{1}\times A_{2}\times \dots A_{6}| = |A_{1}|\times |A_{2}|\times\dots \times|A_{6}| = 26*26*26*10*10*10=26^{3}*10^{3}
$$

