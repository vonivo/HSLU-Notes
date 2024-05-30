Masszahl für den Performance-Gewinn bei der [[Nebenläufigkeit und Parallelität|Nebenläufigkeit]] ist der **Speedup**.
$S = \frac{T_{seq}}{T_{par}}$ 

## Amdahlsches Gesetz
Bei Amdahl wird von einem fest vorgegebenen Programm ausgegangen.
![[Amdahl.png]]
Sprich der Aufwand bleibt bestehen.r
$$
S(N) = \frac{\text{Sequenzielle Laufzeit}}{\text{Parallele Laufzeit}} = \frac{1}{\frac{P}{N} + (1-P)} \implies \frac{1}{1-P} (\lim_{ n \to \infty } )
$$
P = Prozentuale, parallelisierbarer Anteil
N = Anzahl Prozessoren

$\implies$ Der **nicht parallelisierbare Teil** begrentz den Speedup.

## Gesetzt von Gustafson
Gustafson geht von einer Variablen Problemgrösse aus in einem festen Zeitfenster aus.
![[Gustafson.png]]
$$
S(N) = (1-P)+N\times P
$$
$\implies$ Die Anwendung ist Skalierbar.