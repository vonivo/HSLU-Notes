Gleitkommazahlen werden im Dezimal-System wie folgt geschrieben:
$$
n = f\times 10^{e}
$$
Dabei ist eine **Trennung von Präzision und Bereich** erforderlich.

f -> Fraction (Deutsch: Mantisse)
e -> Exponent

### Beispiel
$$
\begin{align}
31.4 &= 3.14 \times 10^{-1} \\
19410000 &= 1.941 \times 10^{8} \\
0.00000243 &= 2.43 \times 10^{-6} 
\end{align}
$$


## IEEE 754
![[IEEE754.png]]
Insgesamt wird eine Zahl mit 32 Bit (4 Byte) abgespeichert.

Sign:          1-Bit (0: plus, 1: minus)
Exponent:  8-Bit Exponent wird mit dem [[Negative Binärzahlen#Exzesscode|Exzesscode]] (127) abgespeichert
Fraction:    23-Bit. Hier wird nur alles hinter dem Punkt abgespeichert, da in Binär die Zahl vor dem Punkt immer '1' ist. (Also somit eigentlich 24-Bit Fraction)

### Konvertierung der Zahl 432
1. 432 in Binär umwandel:
$$
432 = 0001'1011'0000.0000'000
$$
2. Punkt verschieben:
$$
0001.1011 \times 2^{8}
$$
3. Der Exponent in Exzesscode Umwandeln
$$
\begin{align}
8 + 127 &= 135 \\
135 &= 1000'0111 
\end{align}
$$
4. Zahl zusammenstellen:
$$
\begin{align}
\text{1. Sign-Bit}\to \text{hier 0 da positiv} \\
&=0'00000000'00000000000000000000000 \\
\text{2. Exponent in Exzesscode}  \\
&= 0'10000111'00000000000000000000000 \\
\text{3. Fraction} \\
&=0'10000111'10110000000000000000000 \\
\text{4. Formatieren} \\
&=0100'0011'1101'1000'0000'0000'0000'0000 \\
\text{5. in HEX umwandeln} \\
&= 43'D8'00'00
\end{align}
$$


