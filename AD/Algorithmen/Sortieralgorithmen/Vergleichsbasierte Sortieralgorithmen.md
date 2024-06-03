Bei vergleichsbasierten [[Sortieralgorithmus|Sortieralgorithmen]] sind die Vergleichsoperationen massgebend für die [[AD/Algorithmen/Komplexität|Rechenzeit]].
Sie sind **bestenfalls** (wenn überhaupt möglich) mit der [[AD/Algorithmen/Komplexität|Zeitkomplexität]] vom $O(n \times\log n)$ lösbar.

## Beispiel
Es existieren die Datenelemente D1, D2, D3, D4 ($n = 4$).
Dabei ist D1 das kleinste Element und D4 das grösste.

Mit $n=4$ sind insgesamt $n! = 24$ verschiedene Ausgangssituationen für das Sortieren möglich.

### Entscheidungsbaum
Im Entscheidungsbaum repräsentiert jedes Blatt **genau eine der $n!$ möglichen Ausgangssituationen**, welche durch die Konten (Vergleiche) differenziert werden.
![[Sort_Decision_tree.png]]
Die Pfeile zeigen an, wie welche Elemente vertausch werden müssen, damit diese sortiert sind. Dies könnte man fix einprogrammieren und dann sortieren (mit einer [[AD/Algorithmen/Komplexität]] von $O(1)$. (Nur für das Sortieren anhand der Pfeile)).

Mit einem [[Binäre Bäume|binären Baum]] kann man alle $n!$ Ausgangssituationen differenzieren, wobei jeder innere Knoten einem Vergleich entspricht.

Damit alle Ausgangssituationen differenziert werden können, sind anhand der [[Höhe eines Baumes]] $h$ **mindestens $(h-1)$** Vergleiche notwendig. 
Bei einem [[Binäre Bäume|binären Baum]] entspricht dies $h \geq \log_{2}(n!) + 1$ und somit $\geq\log n!$ Vergleiche.


### Abschätzung
$$
\begin{align}
\log_{2}(n!) &= \log\left( 1\times2\times3\times4\times\dots \times \frac{n}{2}\times\left( \frac{n}{2}+1 \right) \times(n-1)\times n \right) \\
\end{align}
$$
Setze man nun alle Faktoren auf $n$ erhält man damit sicher ein grösseres Resultat als $\log_{2}(n!)$.
$$
\begin{align}
\implies \log_{2}(n!)&\le\log_{2}(n\times\dots \times n\times n)  \\
&= n \log_{2}(n)
\end{align}
$$

Damit resultiert $\log_{2}(n!) \in O(n*\log n)$, was bedeutet, dass $\log_{2}(n!)$  höchstens so schnell wächst wie $n\log n$.

Lässt man nun die Faktoren $1,2,\dots,\frac{n}{2}$ weg, erhält man ein Resultat das **sicher kleiner** als $\log_{2}(n!)$ ist.
$$
\log_{2}(n!) > \log_{2}\left( \left( \frac{n}{2}+1 \right)\times\dots \times(n-1)\times n \right)
$$
Setzt man nun alle Faktoren auf $\left( \frac{n}{2}+1 \right)$ erhält man ein Resultat, welches **deutlich kleiner** ist.
$$
\begin{align}
\log_{2}(n!)&\gg \log_{2}\left( \left( \frac{n}{2}+1 \right)\times\dots \times\left( \frac{n}{2}+1 \right) \right) \\
&\gg \log_{2}\left( \left( \frac{n}{2}+1 \right)^{n/2} \right) \\
&\gg \frac{n}{2}\log_{2}\left( \frac{n}{2}+1 \right) \\
&\gg \frac{n}{2}\log_{2}\left( \frac{n+2}{2}\right)\\
&\gg \frac{n}{2}(\log_{2}(n+2)-\log_{2}(2))
\end{align}
$$
Lässt man hier nun die Konstanten Faktoren weg und beachtet nur den mächtigsten Summanden (vgl. [[AD/Algorithmen/Komplexität]]) erhält man: $n\log n$.
Somit wächst $\log_{2}(n!)$ **mindestens** so schnell wie $n\log n$.

$\implies$ Daraus resultiert: Vergleichsbasierte Sortierprobleme können bestenfalls mit einer Komplexität von $O(n\log n)$ gelöst werden.

