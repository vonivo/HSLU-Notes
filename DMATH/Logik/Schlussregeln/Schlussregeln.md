---
aliases:
  - logisches Schliessen
---
Bei mathematischen [[Beweise|Beweisen]] geht es darum, mit gültigen Argumenten die Richtigkeit einer Aussage zu begründen.

Dabei ist ein Argument eine folgen von Aussagen die mit einer Konklusion endet.

Gültig heisst, dass die Folgerung aus der Wahrheit der vorhergegangenen Aussagen des Arguments folgt.

**Schlussregeln**
- [[Modus tollens]]
- [[Modus ponens]]
- [[Hypothetischer Syllogismus]]
- [[Disjunktiver Syllogismus]]
- [[Addition]]
- [[Simplifikation]]
- [[DMATH/Logik/Schlussregeln/Konjunktion|Konjunktion]]
- [[Resolution]]

## Beispiel
Zeige, dass die Hypothese "*es ist heute Nachmittag nicht sonnig und es ist kälter als gestern*", "*wir gehen nur schwimmen, falls es sonnig ist*", "*wenn wir nicht schwimmen gehen, machen wir eine Kanufahrt*" und *wenn wir eine Kanufahrt machen, werden wir bis Sonnenuntergang zu Hause sein* um Schluss führt "**wir werden bis Sonnenuntergang zu Hause sein**".

$$
\begin{align}
n &= \text{"Es ist heute Nachmittag sonnig"} \\ 
k &= \text{"es ist kälter als gestern"} \\
s &= \text{"Wir gehen schwimmen"} \\
f &= \text{"Wir machen eine Kanufahrt} \\
h &= \text{"Wir sind bis Sonnenuntergang zu Hause"}
\end{align}
$$
Hypothesen:
$$
\begin{align}
\text{(H1)} & \neg n \land k &\text{"Es ist heute Nachmittag nicht sonning und es ist ..."} \\
\text{(H2)} &s \to n & \text{"wir gehen nur Schwimmen, falls es sonnig ist."} \\
\text{(H3)}&\neg s \to f&\text{"wenn wir nicht schwimmen gehen machen wir ..."} \\
\text{(H4)}&f \to h & \text{"wenn wir eine Kanufahrt machen sind wir bis ..."}
\end{align}
$$
1. [[Simplifikation]]
$$
\begin{align}
&\neg n \land k \\
\hline \\
\therefore &\neg n
\end{align}
$$
2. [[Modus tollens]]
$$
\begin{align}
&\neg n \\
&s \to n \\
\hline \\
\therefore &\neg s
\end{align}
$$
3. [[Modus ponens]]
$$
\begin{align}
&\neg s \\
&\neg s \to f \\
\hline \\
\therefore &f
\end{align}
$$
4. [[Modus ponens]]
$$
\begin{align}
&f \\
&f \to h \\
\hline \\
\therefore &h
\end{align}
$$


