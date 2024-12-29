
>[!Definition]
>Die **erzeugende Funktion** der [[Reelle Zahlenfolgen|Folge]] $a_{0},a_{1},\dots a_{k},\dots(a_{k}\in \mathbb{R})$ ist die unendliche Reihe:
>$$
>G(x)=a_{0}x^{0}+a_{1}x^{1}a_{2}x^{2}a_{3}x^{3}+\dots=\sum_{k=0}^{\infty}a_{k}x^{k}
>$$

**Beispiele**:
$$
\begin{align}
3,3,3,\dots &\to&G(x)=3x^{0}+3x^{1}+3x^{2}+3x^{3}+\dots&=\sum_{k=0}^{\infty}3x^{k} \\
1,2,3,\dots&\to&G(x)=1x^{0}+2x^{1}+3x^{2}+4x^{3}+\dots&=\sum_{k=0}^{\infty}(k+1)x^{k} \\
1,1,1,\dots&\to&G(x)=1x^{0}+1x^{1}+1x^{2}+1x^{3}+\dots&=\sum_{k=0}^{\infty}1x^{k}
\end{align}
$$
**Anwendungsbeispiel**
Wieviele Lösungen hat die Gleichung $x_1 + x_2 + x_3 = 17$ falls für $x_1, x_2, x_3\in \mathbb{N}$ folgende Einschränkungen gelten: $\color{green}2 ⩽ x_1 ⩽ 5, \color{blue}3 ⩽ x_2 ⩽ 6$, und $\color{red}4 ⩽ x_3 ⩽ 7$.

Die Erzeugende Funktion dafür ist:
$$
\begin{align}
G(x)&=(x^{\color{green}2}x^{\color{green}3}x^{\color{green}4}x^{\color{green}5})(x^{\color{blue}3}x^{\color{blue}4}x^{\color{blue}5}x^{\color{blue}6})(x^{\color{red}4}x^{\color{red}5}x^{\color{red}6}x^{\color{red}7}) \\
&=\dots x^{4}x^{6}x^{7}\dots x^{5}x^{5}x^{7}\dots x^{5}x^{6}x^{6}\dots \\
&=\dots3x^{17}\dots
\end{align}
$$

=> Es gibt $3$ Lösungen.

Die erzeugende Funktion wird so generiert, dass jeder Faktor die Werte erlaubt, welche im Exponent die gültigen Werte enthält.
Nun müssen wir diese Funktion so weit ausmultiplizieren, dass wir den Exponenten mit dem gewünschten Resultat ($17$) erhalten. Der Koeffizient vor diesem Faktor gibt an, wie viele Lösungen die Gleichung hat.