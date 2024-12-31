>[!Theorem]
>Seien $a,n\in \mathbb{N}$ mit $ggT(a,n)=1$ (siehe. [[ggT und kgV|ggT]]) und $\phi(n)$ (siehe. [[Eulersche Phi-Funktion]]), dann gilt:
>$$
>a^{\phi(n)}\equiv 1\text{ mod }n
>$$
>Für eine Primzahl $n$ ist dies wegen $\phi(n)=n-1$ der [[Kleiner Satz von Fermat]]($a^{n-1}\equiv 1\text{ mod }n$).

**Beispiel**
Ist $n$ das Produkt zweier verschiendenen [[Primzahl|Primzahlen]] $p$ und $q$, dann gilt $\phi(n)=(p-1)(q-1)$. Dann hat man z.B. $\phi(10)=\phi(2\cdot 5)=4$
Dann gilt:
$$
\begin{align}
3^{4}&\equiv1 \text{ mod 5} \\
7^{4+1}&\equiv 1\text{ mod }10 \to 7^{\phi(10)}\cdot7\equiv 7\text{ mod }10 \\
7^{45}=(7^{4})^{11}\cdot7 &\equiv 7 \text{ mod 10}
\end{align}
$$