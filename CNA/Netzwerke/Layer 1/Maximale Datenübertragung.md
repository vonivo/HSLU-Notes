Die Maximaleübertragungsrate für Signale ist wie folgt defineirt:
$$
R = 2B \log_{2} (n)
$$
$R$ -> Übertragungsrate, [[Datenübertragungsrate]] in Bit/s.
$B$ -> [[Frequenz, Bandbreite|Bandbreite]] der Leitung in Hz.
$n$ -> Anzahl diskreter Singalstufen (Bei Binär 2)


Mit Rauschen:
$$
R = B \log_{2} \left( 1 + \frac{S}{N} \right)
$$$R$ -> Übertragungsrate, [[Datenübertragungsrate]] in Bit/s.
$B$ -> [[Frequenz, Bandbreite|Bandbreite]] der Leitung in Hz.
$\frac{S}{N}$ -> Rauschabstand (Signal-to-Noise)

## Beispiel
3-kHz-Kanal für Binärsignal
$$
\begin{align}
R&=2\times 3kHz \log_{2}(2) \\
&=6\frac{kBit}{s}
\end{align}
$$
3-kHz-Kanal für 4-stufige Signale
$$
\begin{align}
R&=2\times 3kHz \log_{2}(4) \\
&=6\frac{kBit}{s} \times 2 \\
&=8\frac{kBit}{2}
\end{align}
$$
3-kHz-Kanal S/N Verhältnis von 100:1
$$
\begin{align}
R&=\times 3kHz \log_{2}\left( 1+\frac{1000}{1} \right) \\
&=30 \frac{kBit}{s}
\end{align}
$$
