## Arcussinus
Der Sinus (rot) ist im Intervall $\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right]$ bijektiv, und damit umkehrbar. Die [[Umkehrfunktion]] heisst **Arcussinus** (blau).
![[arcsin.png]]
$$
\arcsin:[-1,1] \to \left[ -\frac{\pi}{2}, \frac{\pi}{2} \right]
$$
Dabei gilt:
$$
\begin{align}
\arcsin(\sin x)&=x, \space\space x\in\left[ -\frac{\pi}{2}, \frac{\pi}{2}\right] \\
\sin(\arcsin x)&=x, \space\space x \in [-1,1]
\end{align}
$$
## Arcusconsinus
Analog ist der **Kosinus** im Intervall $[0;\pi]$ umkehrbar; die Umkehrabbildung heisst **Arcusconsinus**:
$$
\arccos: [-1,1]\to[0, \pi], x \mapsto \arccos(x)
$$
und dabei gilt:
$$
\begin{align}
\arccos(\cos x)&=x, \space\space x \in [0,\pi] \\
\cos(\arccos x)&=x, \space\space x \in [-1,1]
\end{align}
$$
## Arkustangens
Schliesslich ist der **Tanges** im Intervall $\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right]$ umkehrbar; die Umkehrabbildung heisst **Arkustangens**:
$$
\arctan:\mathbb{R}\to\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right], x \mapsto \arctan(x)
$$
und dabei gilt:
$$
\begin{align}
\arctan(\tan x) &= x, \space\space x \in \left[ -\frac{\pi}{2}, \frac{\pi}{2} \right] \\
\tan(\arctan x)&=x, \space\space x \in \mathbb{R}
\end{align}
$$

## Ableitung der Arkusfunktionen
Die Ableitung der Arkusfunktionen kann einfach über die [[Ableitung der Umkehrfunktion]] berechnet werden:
$$
\sin(\arcsin x)=x
$$
$$
\begin{align}
(\sin(\arcsin x))' &= (x)' \\
\cos(\arcsin x)\cdot(\arcsin x)'&=1 \\
(\arcsin x)'&=\frac{1}{\cos(\arcsin x)}
\end{align}
$$
Dies kann nur mit dem [[Trigonometrischer Pythagoras|Trigonometrischer Pythagoras]] aufgelöst werden:
$$
\begin{align}
(\arcsin x)'&=\frac{1}{\cos(\arcsin x)} \\
(\arcsin x)'&=\frac{1}{\sqrt{ 1-\sin^2(\arcsin x)}} \\ 
(\arcsin x)'&=\frac{1}{\sqrt{ 1-x^2}}
\end{align}
$$

# Ableitungen der Arkusfunktionen
- $(\arcsin(x))' = \frac{1}{\sqrt{ 1-x^2 }}$
- $(\arccos(x))'=-\frac{1}{1-x^2}$
- $(\arctan (x))' = \frac{1}{1+x^2}$
