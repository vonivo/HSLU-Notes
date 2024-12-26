>[!Theorem]
>Kann ein **erstes Ereignis auf $n_{1}$ Arten eintreten** und ein zweites Ergeignis auf $n_{2}$ Arten, wobei **nicht beide Ereignisse gelichzeitig eintreten können**, dann können die beiden Ereignisse auf $n_{1}+n_{2}$ Arten eintreten.

### Beispiel
Ein Student kann seine Projektarbeit aus drei Listen mit je $23$, $15$ bzw. $19$ Arbeiten auswählen. Aus wie vielen Projekten kann er auswählen?

**Lösung:** Aus der ersten Liste hat er $23$, aus der zweiten $15$ und aus der dritten $19$ Möglichkeiten.
Also => $23+15+19=57$ Möglichkeiten.

## Summenregel und [[Megneoperationen#Vereinigung|Vereinigung von Mengen]]

Für die Menge der Elemente einer Vereinigung **paarweiser disjunkter Mengen** $(\forall i\forall j(A_{i}\cap A_{j}=\emptyset|j\neq i))$ gilt die Summenregel
$$
|A_{1}\cup A_{2}\cup\dots A_{n}| = |A_{1}| + |A_{2}| + \dots |A_{n}|
$$

=> Komplexe Zählprobleme lassen sich oft durch Anwendung der[[DMATH/Zählen/Produktregel|Produkt-]] und Summenregel lösen.

### Beispiel
Ein gültiges Passwort besteht aus sechs bis acht Zeichen (Grossbuchstaben und Ziffern) wobei mindestens eine Ziffer vorhanden sein muss. Wie viele Passwörter gibt es?
$$
\begin{align}
P_{6}^{u}&= \text{\#Ungültige Passwörter der Länge 6} \\
P_{6}^{g}&=\text{\#Gültige Passwörter der Länge 6} \\
P_{6}&=\text{\#Aller Passwörter der Länge 6}
\end{align}
$$
$$
\begin{align}
P_{6} &= 36^{6} \\
P_{6}^{u}&=26^{6} \\
P_{6}^{g}&=P_{6}-P_{6}^{u} &=36^{6}-26^{6}
\end{align}
$$
=> Analog wird das mit $P_{7}$ und $P_{8}$ gemacht und man erhält:
$$
(36^{6}-26^{6})+(36^{7}-26^{7})+(36^{8}-26^{8})
$$

