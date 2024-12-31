- Schlüssel der gleich Lang ist wieder der Text
- Darf nur einmal verwendet werden
- sicher

## Schlüssel darf nicht wiederverwendet werden:
$$
\begin{align}
m\oplus k &=c \\
m'\oplus k&=c' \\
 \\
\implies c\oplus c'&=(m\oplus k)\oplus(m'\oplus k) \\
&=m\oplus k\oplus m'\oplus k \\
&=(m\oplus m')\oplus (k\oplus k) \\
&=(m\oplus m')
\end{align}
$$

## Auf 3 Personen aufteilen
Das Geheimnis $m=10111010011$ soll auf 3 Personen aufteilt werden.

=> es werden folgende Bitstring generiert:
$$
\begin{align}
c_{1}&=10101010111&\text{zufällig generiert} \\
c_{2}&=01010101011&\text{zufällig generiert} \\
c_{3}&=m\oplus(c_{1}\oplus c_{2})
\end{align}
$$

Zeigen dass das Geheimnis durch $m=c_{1}\oplus c_{2}\oplus c_{3}$ rekonstruiert wird.
$$
\begin{align}
c_{3}&=m\oplus(c_{1}\oplus c_{2}) \\
c_{3}\oplus (c_{1} \oplus c_{2})&=(m\oplus(c_{1}\oplus c_{2}))\oplus(c_{1}\oplus c_{2}) \\
c_{3}\oplus c_{1} \oplus c_{2}&=m\oplus c_{1}\oplus c_{2} \oplus c_{1}\oplus c_{2} \\
c_{3}\oplus c_{1} \oplus c_{2}&=m
\end{align}
$$