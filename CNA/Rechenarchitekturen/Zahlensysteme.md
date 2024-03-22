#flashcards/Rechenarchitekturen 
Ein Zahlensystem ist wie folgt aufgebaut:
Es gibt die ganz normalen Stellen, welche dann einen Stellenwert erhalten.


| $10^{3}$ | $10^{2}$ | $10^{1}$ | $10^{0}$ |
| -------- | -------- | -------- | -------- |
| 1        | 0        | 2        | 3        |
Das ergibt dann folgende Zahl:
$$\begin{align}
1*10^{3}+0*10^{2}+2*10^{1}+3*10^{0}&=1023 \\
1*1000+0*100+2*10+3*1&=1023 \\
1000+20+3&=1023
\end{align}$$
Den Stellenwert ergibt sich immer aus der Basis (Anzahl verschiedener Zeichen) hoch die Stelle.
Beim Binären z.B.:

| $2^{3}$ | $2^{2}$ | $2^{1}$ | $2^{0}$ |     |
| ------- | ------- | ------- | ------- | --- |
| 1       | 0       | 1       | 1       |     |
$$\begin{align}
1*2^{3}+0*2^{2}+1*10^{1}+1*2^{0}&=11 \\
1*8+0*4+1*2+1*1&=11 \\
8+2+1&=11
\end{align}$$

## Binary Coded Decimal (BCD)
>[!error]
>Jede Ziffer im Dezimalsystem wird als 4-bit-Zahl dargestellt
>Bsp: ${\color{red}8}{\color{green}5}{\color{blue}3}{\color{yellow}9} = {\color{red}1000}\space{\color{green}0101}\space{\color{blue}0011}\space{\color{yellow}1001}$
>Es werde ein oder 2 BCD-Ziffern in einem Byte gespeichert.


# Kontrollfragen
**Welche anderen Stellenwertsysteme kennen Sie?**
?
12er-System, Octal (8), Hexadezimal usw.
