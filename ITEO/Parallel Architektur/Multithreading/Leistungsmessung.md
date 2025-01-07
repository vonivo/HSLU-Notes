Eine einfache Leistungsmessung für das Speedup des [[Multithreading]] sind folgenden Formel:

$$
\begin{align}
n&:\text{Anzahl Prozessoren} \\
V(n)&: Leistungsverbesserung \\
E(n)&:\text{Effizenz} \\
T(1)&:\text{Aufführungszeit für einen Prozessor} \\
T(n)&:\text{Aussführungszeit für n Prozessoren}
\end{align}
$$
$$
\begin{align}
V(n)&=\frac{T(1)}{T(n)} \\
E(n)&=\frac{V(n)}{n}
\end{align}
$$
![[Pasted image 20250106201221.png]]
Die Kurve ist nciht linear, da immer ein Overhead hinzukommt, um alles zu administrieren.