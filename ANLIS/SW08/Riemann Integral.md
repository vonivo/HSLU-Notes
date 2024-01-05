Das bestimmte Integral wird benutzt, um die Fläche unter einer [[Funktion]] zu bestimmen:
![[Bestimmtes_Integral.png]]
Hier wird die Fläche von $x_{0} = 1$ bis $x_{5}=2$ bestimmt. Nun werden immer Rechtecke gebildet wie obigen Bild ersichtlich. Dabei wird dann die Fläche dieser Rechte addiert und man bekommt eine Näherung an die Fläche unterhalb des Grafen.

Im obigen Bild wird die sogenannte **Obersumme** berechnet. 
Das Gegenteil dazu ist die **Untersumme**:![[Untersumme.png]]
Wenn wir jetzt immer mehr Rechtecke bilden wird die Näherung immer genauer, d. h. bei unendlich vielen Rechtecken ist die Näherung exakt.

Das bestimmte Integral wird so geschrieben:
$$
\int_{a}^b f(x) \, dx 
$$

>[!info]
>Ist $f$ stetig im Intervall $[a,b]$, dann ist $f$ über $[a,b]$ integrierbar und die Nettofläche zweichen $O(f)$ und $[a,b]$ ist
>$$
>A = \int _{a}^b  f(x)\, dx.
>$$

>[!warning]
>Flächen unterhalb der x-Achse werde **negativ** und solche oberhalb **positiv** gezählt.

## Eigenschaften
- $\int _{c}^cf(x) \, dx = 0$
- $\int _{a}^b f(x) \, dx = -\int _{b}^a f(x) \, dx$

## Beispiel
Wir berechnen $\int _{1}^2 x^{2}\, dx$ indem wir die n-te Obersumme berechnen.
Das heisst wir haben $n$-Teilsummen und der Abstand ist $\Delta x = \frac{2-1}{n} = \frac{1}{n}$ (Breite der Rechtecke).

Um jetzt die Verschiedenen $x_{k}$ zu bekommen, rechnen wir:
$$
x_{k} = x_{0}+k\Delta x = x_{0}+\frac{k}{n} = 1+\frac{k}{n}
$$

Die **Obersumme** eines solchen Rechtecks ist nun
$$
Fläche = f(x_{k})\Delta x = x_{k}^2\Delta x = \left( 1+\frac{k}{n} \right)^2\cdot \frac{1}{n}
$$
Nun bilden wir die Summe daraus:
$$
\begin{align}
\sum_{k=1}^{n}f(x_{k})\Delta x &= \sum_{k=1}^{n}\left( 1+\frac{k}{n} \right)^2\cdot \frac{1}{n} \\
&= \frac{1}{n}\sum_{k=1}^{n}\left(1+ \frac{k}{n} \right)^2 \\
&= \frac{1}{n}\sum_{k=1}^{n}\left(1+ \frac{k}{n} \right)\left(1+ \frac{k}{n} \right) \\
&=\frac{1}{n}\sum_{k=1}^{n}\left(1+2 \frac{k}{n}+\left( \frac{k}{n} \right)^2 \right) \\
&=\frac{1}{n}\left[\sum_{k=1}^{n}1+ \frac{2}{n} \sum_{k=1}^{n} k + \frac{1}{n^2}\sum_{k=1}^{n}k^{2}\right]
\end{align}
$$
Nun können wir mithilfe der [Faulhaberschen Formeln](https://de.wikipedia.org/wiki/Faulhabersche_Formel) Die Summen bestimmen.
$$
\begin{align}
&= \frac{1}{n}\left[ n + \frac{2}{n} \frac{n(n+1)}{n} + \frac{1}{n^2} \frac{n(n+1)(2n+1)}{6}\right] \\
&=\frac{1}{n}\left[ n + \frac{2}{n} \frac{n(n+1)}{2} + \frac{1}{n^2} \frac{n(n+1)(2n+1)}{6}\right]  \\
&=\frac{1}{n}\left[ n +  \frac{n(n+1)}{n} + \frac{(n+1)(2n+1)}{6n}\right]  \\
&=\frac{1}{n}\left[ n +  \frac{n^2+n}{n} + \frac{(n+1)(2n+1)}{6n}\right]  \\
&= 1 +  \frac{n^2+n}{n^2} + \frac{(n+1)(2n+1)}{6n^2} \\
&= 1 +  \left( 1+\frac{1}{n} \right) + \frac{1}{6}\frac{(n+1)(2n+1)}{n^2} \\
&= 1 +  \left( 1+\frac{1}{n} \right) + \frac{1}{6} \frac{n+1}{n} \frac{2n+1}{n} \\
&= 1 +  \left( 1+\frac{1}{n} \right) + \frac{1}{6} \left( 1+\frac{1}{n} \right) \left( 2+\frac{1}{n} \right) \\
\end{align}
$$
Wenn wir nun den Limes gegen $\infty$ setzen passiert folgendes:
$$
\begin{align}
&\lim_{ n \to \infty } (1 +  \left( 1+\frac{1}{n} \right) + \frac{1}{6} \left( 1+\frac{1}{n} \right) \left( 2+\frac{1}{n} \right)) \\
&=1+\lim_{ n \to \infty } \left(1 +  \left( 1+\frac{1}{n} \right)\right)+\lim_{ n \to \infty } \left(\frac{1}{6} \left( 1+\frac{1}{n} \right) \left( 2+\frac{1}{n} \right))\right) \\
&=1+1+\lim_{ n \to \infty }\left(\frac{1}{n}\right)+\lim_{ n \to \infty }  \left( \frac{1}{6}+\frac{1}{6n}\right) \left( \frac{2}{6}+\frac{1}{6n} \right) \\
&=1+1+\lim_{ n \to \infty }\left(\frac{1}{n}\right)+\frac{1}{6}+ \frac{2}{6}+\lim_{ n \to \infty }  \left(\frac{1}{6n}\right) \left(+\frac{1}{6n} \right) \\
&=1+1++\frac{1}{6}+ \frac{2}{6} \\
&= 2+\frac{1}{3}
\end{align}
$$

