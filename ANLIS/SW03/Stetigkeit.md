Eine [[Funktion]] $f$ heisst dann stetig, wenn man ihren Graphen zeichnen kann, ohne den Stift absetzen zu müssen.

Genauer ist eine Funktion $f$ stetig an der Stelle $a$ falls:
1. Die Funktion $f$ dort existiert, d. h. falls $f(a)$ definiert ist ($a$ in der [[Definitionsbereich|Definitionsmenge]])
2. links- und rechtsseitiger [[Grenzwert]] existieren und gleich sind
$$
\lim_{ x \to a^- }f(x)=\lim_{ a \to x^+ } f(x)=\lim_{ a \to x } f(x) 
$$
3. und die genannten Grenzwerte mit dem Funktionswert übereinstimmen
$$
\lim_{ x \to a^- }f(x)=\lim_{ a \to x^+ } f(x)= f(x) 
$$

**Zusammengefasst:** $f$ ist stetig an der Stelle $a$, falls:
$$
\lim_{ x \to a^- }f(x)=\lim_{ a \to x^+ } f(x)= f(x) 
$$
und a in $\mathbb{D}(f)$ existiert.


Eine Funktion heisst stetig, falls sie überall in ihrem [[Definitionsbereich]], d. h. $\forall x \in \mathbb{D}(f)$ stetig ist.

>[!info]
>Ist $f$ im Intervall $[a,b]$ stetig, dann nimmt $f$ zwischen $f(a)$ und $f(b)$ jeden Werte mindestens einmal an.



## Rechenregeln,
- Summe und Differenz stetiger Funktionen sind stetig.
- Der Quotient zweier stetiger Funktionen ist dort stetig, wo der Nenner nicht verschwindet.
- Polynome $P(x) = \sum_{k=0}^n a_{k}k^k$ sind stetig.
- [[Rationale Funktionen]] $r(x)=\frac{P(x)}{Q(x)}$ sind dort stetig, wo das Nennerpolynom $Q(x)$ nicht verschwindet.
- Sinusfunktionen und Kosinusfunktion sind stetig.
- Der Tanges ($\tan x = \frac{\sin x}{\cos x}$) ist stetig, falls $\cos x\ne 0$, d. h. $x\ne \frac{\pi}{2} + k\pi, k\in\mathbb{Z}$
- [[Exponentialfunktionen|Exponential]]- und [[Logarithmusfunktionen]] sind in ihren [[Definitionsbereich|Definitionsberichen]] stetig.
- Zusammensetzung stetiger [[Funktion]] ist stetig.
- Eine [[Zusammengesetzte Funktionen|zusammengesetzt Funktion]] kann dort unstetig sein, wo eine der verwendeten Funktionen nicht stetig ist.