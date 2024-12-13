Die Umkehrfunktion einer [[ANLIS/SW01/Funktionen/Funktion]] existiert, falls für jedes $y$ genau ein $x$ existiert.
Sodass:
$$
f(x) = y \Longleftrightarrow f^{-1}(y)=x
$$

>[!info]
>Die Funktion $y=f(x)$ hat genau dann eine Inverse, wenn ihr Graph von jeder Paralleln zur x-Achse höchstens einmal geschnitten wird.

Wenn dies nicht der Fall ist, kann eine Funktion jedoch in einem Teil-[[Definitionsbereich]] umgekehrt werden.

## Vorgehen
Um eine Funktion zu invertieren, muss die Funktionsgleichung nach $x$ aufgelöst und danach die Variablen vertauscht werden.

$$
\begin{align}
y &= x^3 \\
y^{\frac{1}{3}}&=x \\
f^{-1}(x) = x^{\frac{1}{3}}&=y
\end{align}
$$
![[Umkehrfunktion.png]]

## Die Umkehrfunktion zusammengesetzt
Wird nun $f(x)\circ f^{-1}(x)$ oder $f^{-1}(x)\circ f(x)$ geschrieben kommt immer $x$ raus:
$$
f(f^{-1}(x)) =x
$$
$$
f^{-1}(f(x))=x
$$
