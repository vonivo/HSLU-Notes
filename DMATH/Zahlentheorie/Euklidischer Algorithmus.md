>[!Theorem]
>Seien $a,b\in\mathbb{Z}$ mit $a>b$. Dann gilt:
>$$
>\begin{align}
a&=q_{1}\cdot b+r_{1} &0\leq r_{1}<b &\text{ ggT}(a,b) &=ggT(b,r_{1}) \\
b&=q_{2}\cdot r_{1}+r_{2}&0\leq r_{2}\le r_{1} &ggT(b,r_{1}) &=ggT(r_{1},r_{2}) \\
r_{1}&=q_{3}\cdot r_{2}+r_{3}&0\leq r_{3}\le r_{2} &ggT(r_{1},r_{2}) &=ggT(r_{2},r_{3}) \\
\\ \\
r_{t-1}&=q_{t}\cdot r_{t-1}+r_{t}&0\leq r_{t}\le r_{t-1} &ggT(r_{t-2},r_{t-1}) &=ggT(r_{t-1},r_{t}) \\
r_{t}&=q_{t+1}\cdot r_{t}&&ggT(r_{t-1},r_{t}) &=ggT(r_{t},0)
\end{align}
>$$
>Dabei is $r_{t}$ der letze nicht verschwindende Rest und dieser ist gleich dem $ggT(a,b)$.

>[!Theorem]
>Sien $a$ und $b$ natürliche Zahlen mit $a\geq b>0$. Dann ist die **Anzahl Divisionen** im Euklidischen Algorithmus um das $ggT(a,b)$ zu finden **nicht grösser als 5-Mal die Anzahl Ziffern von $b$**.




![[Pasted image 20241215201921.png]]
Der Euklidische Algrorithmus kann mit Modulo verschnellert werden:
$$
ggT(a,b) = ggT(b,a\text{ mod }b)
$$







