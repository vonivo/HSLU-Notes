>[!Definition]
>ein Derangement ist eine [[Permutationen|Permutation]], die kein Objekt am selben Platz lässt.

>[!Theorem]
>Die Anzahl der Drangements bei einer [[Menge]] von $n$ Elementen ist:
>$$
>D_{n}=n!\left[1-\frac{1}{1!}+\frac{1}{2!}-\frac{1}{3!}+\dots+(-1)^{n}\frac{1}{n!}\right]
>$$

**Beispiel**
Es werden $100$ Briefe zufällig in $100$ adressierte Umschläge gesteckt, mit welcher [[Wahrscheinlichkeit]] befindet sich kein Brief im richtigen Umschlage?
$$
\begin{align}
p&=\frac{\text{\# günstige Fälle}}{\text{\# mögliche Fälle}} \\
&=\frac{100!\left[1-\frac{1}{1!}+\frac{1}{2!}-\frac{1}{3!}+\dots+(-1)^{100}\frac{1}{100!}\right]}{100!} \\
&=\left[1-\frac{1}{1!}+\frac{1}{2!}-\frac{1}{3!}+\dots+\frac{1}{100!}\right] \\
&\approx e^{-1}=\frac{1}{e}=0.368
\end{align}
$$
