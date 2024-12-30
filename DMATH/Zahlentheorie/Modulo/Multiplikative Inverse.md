- In $\mathbb{Z}$ hat fast kein Element eine multiplikatives Inverses. Die Gleichung $x\cdot y=1$ hat in $\mathbb{Z}$ nur die Lösung $1\cdot 1=1$ und $(-1)\cdot(-1)=1$.
- In $\mathbb{R}$ hat jedes Element bis auf $0$ ein Inverses, denn $x\cdot \frac{1}{x}=1$.
- Erstaunlicherweise haben in $\mathbb{Z}_{n}$ viele Elemente ein multiplikatives Inverses.

## $\mathbb{Z}_{n}$
>[!Definition]
>Die Modulare Inverse ist die Zahl $x^{-1}$ mit welcher sich die Zahl $x$ multiplizieren lässt, damit $x\cdot x^{-1}\text{ mod n }= 1$ ergibt.

>[!Theorem]
>Sei $n$ eine natürliche Zahl und $a \in \mathbb{Z}_{n}$. Dann hat $a$ genau dann ein Inverses bezüglich der Multiplikation $\odot_{n}$ in $\mathbb{Z}_{n}$ ([[Modulare Rechenoperationen]]), wenn $ggT(a,n)=1$ gilt.

Die Menge aller Invertierbaren Elemente in $\mathbb{Z}_{n}$ wird mit $\mathbb{Z}_{n}^{*}$ bezeichnet. Es gilt also:
$$
\mathbb{Z}_{n}^{*}=\{ a\in \mathbb{Z}_{n}|a>0\land ggT(a,n)=1 \}
$$
Somit liefert die [[Eulersche Phi-Funktion|euler'sche Phi-Funktion]] von $n$ wegen $\phi(n)=|\mathbb{Z}_{n}^{*}|$ genau die Anzahl invertierbarer Elemente kleiner als $n$.


**Beispiel**
$$
\begin{align}
x&=3 \\
x^{-1}&=2 \\
n&=5 \\
 \\
x\cdot x^{-1}\text{ mod } n &=1 \\
3\cdot{2}\text{ mod }5&=1
\end{align}
$$
=> $x\cdot x^{-1}\equiv1(\text{mod }n)$

Um das Modulare Inverse einer Zahl zu finden, kann die [[Diophantische Gleichung]] Gleichung verwendet werden:
$$
\begin{align}
n_{1}x+n_{2}y&=1 \\
n_{1}x&=1-n_{2}y \\
n_{1}x&\equiv 1 (\text{ mod }n_{2})
\end{align}
$$

## Inverse berechnen mit dem [[Kleiner Satz von Fermat|kleinen Satz von Fermat]]
Sei $p$ ein [[Primzahl]]. In diesem Fall kann der [[Kleiner Satz von Fermat]] genutzt werden, um die Inversen systematisch zu bestimmen. Sei $a\in\mathbb{Z}_{p}^{*}={1,2,\dots p-1}$ dann gilt:
$$
a^{p-1}=a\cdot a^{p-2}=a\cdot a^{-1}\equiv1\text{ mod }p
$$
und somit
$$
a\odot_{p}R_{p}(a^{p-2})=1
$$
d.h. $a^{-1}=R_{p}(a^{p-2})=a^{p-2} \text{ mod p}$ ist das Inverse zu $a$ modulo $p$.

**Beispiel**
Bestimme alle Inversen in $\mathbb{Z}_{5}^{*}=\{ 1,2,3,4 \}$
$$
\begin{align}
1^{-1} &= 1^{5-2} \text{ mod 5} &&=1 \\
2^{-1} &= 2^{5-2} \text{ mod 5} &=8 \text{ mod 5}&=3 \\
3^{-1} &= 3^{5-2} \text{ mod 5} &=27 \text{ mod 5}&=2 \\
4^{-1} &= 4^{5-2} \text{ mod 5} &=64 \text{ mod 5}&=4
\end{align}
$$
