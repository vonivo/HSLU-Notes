Bei Wachstumsprozessen trifft man sehr oft auf die Exponentialfunktion.

## Definition
Die Exponentialfunktion $P(t)$ ist wie folgt definiert:
$$
\begin{align}
P(t) &= P(t-1)*b \\
P(t) &= P(t-2)*b^2 \\
&\dots \\
P(0) &= b^t \\
P(t) &= a*b^t
\end{align}
$$

>[!info]
>Eine Funktion der Form $f(x)=a*b^x$ mit $b\gt0$ und $b\ne 1$ heisst **Exponentialfunktion**. $a$ heisst **Anfangswert** und $b$ heisst **Wachstumsfaktor**. Für [[Definitionsbereich|Definitions]]- und [[Wertebereich]] gilt: $\mathbb{D}(f)=\mathbb{R}, \mathbb{W}(f)=\mathbb{R}^+$.


## Wachstumsfaktor
Exponentialfunktionen ist eine Form von [[ANLIS/SW01/Funktionen/Funktion|Funktionen]] bei welchen der **Wachstumsfaktor** $b$ (z. B. $1.3\%$) konstant bleibt.
Er ist definiert durch:
$$
b = \frac{P(t)}{P(t-1)} = \text{konstant}
$$

## Basiswechsel
Jede Exponentialfunktion $y=b^x$ mit $b \gt 1$ kann als Exponentialfunktion zur Basis $e=2.71828...$ oder irgendeiner anderen Basis $a \gt 0$ $(a\ne 0)$ dargestellt werden.
$$
\begin{align}
b^x&=e^{kx} \\
\ln(b^x) &= \ln(e^{kx}) \\
x\ln b&= kx\ln e \\
x\ln b=kx \\
\ln b=k \\
\end{align}
$$
dementsprechend:
$$
b^x=e^{x\ln b}
$$
