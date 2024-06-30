Die Zyklische Redundanzprüfung CRC (Cyclic Redundancy Check) ist ein mathematisches Modell zur Erzeugung einer effizienten Prüfsumme.

Für den CRC wird einen Bitfolge $b_{m-1}b_{m-2}\dots b_{1}b_{0}$ wird als Koeffizienten eines Polynoms $P(x)$ des Grades $m-1$ interpretiert:
$$
P(x) = b_{m-1}x^{m-1}+b_{m-2}x^{m-2}+\dots+b_{1}x+b_{0}
$$
Beispiel mit 8 Bit:
`10011001`:
$$
\begin{align}
&=1x^{7}+0x^{6}+0x^{5}+1x^{4}+1x^{3}+0x^{2}+0x^{1}+1 \\
&=x^{7}+x^{4}+x^{3}+1
\end{align}
$$


# Ablauf
1. Erzeugen eines Generator-Polynom $G(x)$ vom Grad $n$
2. $P(x)$ wird recht um $n$ Bits erweitert, so dass ein neues Polynom $T(x)$ entsteht.
3. Mit einem einfachen Algorithmus werden die $n$ Bits so bestimmt, dass $\frac{T(x)}{G(x)}$ **ohne Rest** Teilbar ist.
	1. $T_{0}(x) = P(x)$ mit $n$ Nullen rechts erweitern.
	2. $\frac{T_{0}(x)}{G(x)}$ = ganzes Ergebnis + Rest
	3. $T(x) =  T_{0}(x) + Rest$
4. Das $T(x)$ entsprechende Wort wird übertragen.
5. Beim Empfänger wird überprüft ob $\frac{T(x)}{G(x)}$ ohne Rest teilbar ist.
	- Ja -> 99.99 % kein Fehler
	- Neine -> Fehler

Es werden so fast alle Fehler erkannt. Eine Ausnahme ist, wenn der Fehler einem Vielfachen von $G(x)$ entspricht.

-> Auch Burstfehler bis zur Länge $n+1$ werden erkannt.


# Beispiel
## Berechnen
Generator-Polynom: `101` 
Grad: 2
Nachricht: $\color{green}1101$
![[CRC_1.png]]
- Die violett eingefärbten Operation ist eine XOR-Operation.
- Die graueingefärbtenn Zeichen ist die Spezial-Maske. Sie wirdgesetzt, wennn die obere Zeile mit einer 0 beginnt.

=> Nachricht: ${\color{yellow}1101}\color{blue}10$

## Überprüfen
Frame: `1101011011`
Generator: `1001`
N: `4`
![[CRC_2.png]]

Wird die Null-Maske verwendet, wird beim Resultat einen 0 gesetzt, ansonsten eine 1.

# Realisierung
Eine einfache technische Realisierung zur Bestimmung von $T(x)$ is ein rückgekoppeltes Schieberegister der Länge $n$.
![[CRC_3.png]]

# Wichtige Generator-Polynome

| Protokoll       | Generatorpolynom                                                                            |
| --------------- | ------------------------------------------------------------------------------------------- |
| CRC-16          | $x^{16}+x^{15}+x^{2}+1$                                                                     |
| CRC-CCITT, HDLC | $x^{16}+x^{12}+x^{5}+1$                                                                     |
| CMS/CD          | $x^{32}+x^{26}+x^{23}+x^{22}+x^{16}+x^{12}+x^{11}+x^{10}+x^{8}+x^{7}+x^{5}+x^{4}+x^{2}+x+1$ |
| HEC             | $x^{8}+x^{2}+x+1$                                                                           |

**CRC-16, CRC-CCIT**
- alle ungeraden Bitfehler für Blöcke bis 4095 Bytes erkannt
- alle 1-Bit-Fehler für Blöcke bis 4095 werden erkannt
- alle Fehlerbursts bis 16 Bit Länge werden erkannt
- 99.997 % aller längeren Fehlerbursts werden erkannt.