## Areasinus
Der [[Hyperbolische Funktionen|Sinus hyperbolicus]] ist bijektiv und damit umkehrbar. Die [[Umkehrfunktion]] heisst **Areasinus**:
$$
\operatorname{arsinh}:\mathbb{R}\to \mathbb{R}, x \mapsto \operatorname{arsinh}x = \ln(x+\sqrt{ x^2+1 })
$$
Es gilt:
$$
\begin{align}
\operatorname{arsinh}(\sinh x) =x, \space\space x \in \mathbb{R} \\
\sinh(\operatorname{arsinh}(x)) =x, \space\space x \in \mathbb{R} \\
\end{align}
$$
## Areakonsinus
Anslog kann man den [[Hyperbolische Funktionen|Kosinus hyperbolicus]] für $x\gt_{0}$ umkehren: die [[Umkehrfunktion]] heisst **Areakosinus** und ist definiert durch:
$$
\operatorname{arcosh}:[1;\infty]\to \mathbb{R}_{0}^+, x \mapsto \operatorname{arcosh}x = \ln(x+\sqrt{ x^2-1 })
$$
und es gilt:
$$
\begin{align}
\operatorname{arcosh}(\cosh x) =x, \space\space x \in \mathbb{R}_{0}^+ \\
\cosh(\operatorname{arcosh}(x)) =x, \space\space x \in [1;\infty] \\
\end{align}
$$
## Areatangens
Ebenso hat der [[Hyperbolische Funktionen|Tangens hyperbolicus]] die [[Umkehrfunktion]] **Areatangens**:
$$
\operatorname{artanh}:[-1,1]\to \mathbb{R}, x \mapsto \operatorname{artanh}x =\frac{1}{2}\ln\left(\frac{1+x}{1-x}\right)
$$und es gilt:
$$
\begin{align}
\operatorname{artanh}(\tanh x) =x, \space\space x \in \mathbb{R} \\
\tanh(\operatorname{artanh}(x)) =x, \space\space x \in [-1;1] \\
\end{align}
$$

## Ableitungen
Die Ableitung der [[Hyperbolische Funktionen|hyperbolischen Funktionen]] wird mittels [[Ableitung der Umkehrfunktion]] gemacht und man erhält:
- $[\operatorname{arsinh}x]' = \frac{1}{\cosh(\operatorname{arsinhx})}=\frac{1}{\sqrt{ 1+(\sinh(\operatorname{arsinhx})^2) }}= \frac{1}{\sqrt{ 1+x^2 }}$
- $[\operatorname{arcosh}x]' = \frac{1}{\sqrt{ x^2-1 }}, x\gt1$
- $[\operatorname{artanh}x]' =\frac{1}{1-x^2}, x \lt 1$