- $(\sin x)' = \cos x$
- $(\cos x)'=-\sin x$
- $(-\sin x)' = -\cos x$
- $(-\cos x)'=\sin x$
- $(\tan x)' = 1+\tan^2(x)$ oder $(\tan x)' = \frac{1}{\cos^2 x}$

## Herleitung
$$
\begin{align}
\frac{d}{dx}(\sin x) &=\lim_{ \Delta x \to 0 } \frac{\sin (x + \Delta x)-\sin x}{\Delta x} \\
&=\lim_{ \Delta x \to 0 } \frac{\sin (x)\cos\Delta x+ \sin \Delta x \cos x-\sin x}{\Delta x} \\
&= \lim_{ \Delta \to x } \left[\frac{\sin(\Delta x)}{\Delta x}\cdot\cos(x)+\sin x \cdot \frac{\cos x - 1}{\Delta x}\right] \\
&= \cos(x)\cdot\lim_{ \Delta \to x } \frac{\sin(\Delta x)}{\Delta x}+\sin x \cdot \lim_{ \Delta x \to 0 } \frac{\cos x - 1}{\Delta x} \\
&= \cos(x)\cdot1+\sin x \cdot 0 \\
&= \cos x
\end{align}
$$
Hierfür wurde das [[Additionstheorem]] und schon die bekannten [[Grenzwert|Grenzwerte]] $\lim_{ x \to 0 }\frac{\sin x}{x} = 1$ und $\lim_{ x \to 0 }\frac{\cos x -1}{x}= 0$ verwendet.
