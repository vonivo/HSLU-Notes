Die Cramersche Regel ist ein verfahren zur Lösung eines [[Lineare Gleichungsysteme|linearem Gleichungssystem]] mittels der [[Determiante]].
## Cramersche Regel 2x2
Gleichungssystem:
$$\begin{align}
\color{green}a_{1}\color{white}x + \color{red}b_{1}\color{white}y &= \color{blue}c_{1} \\
\color{green}a_{2}\color{white}x + \color{red}b_{2}\color{white}y &= \color{blue}c_{2} \\
\end{align}$$

Koeffizientenmatrix:
$$
\begin{pmatrix}
	\color{green}a_{1} & \color{red}b_{1} \\
\color{green}a_{2} & \color{red}b_{2} 
\end{pmatrix}$$
Lösungsvektor
$$\vec{c} = \begin{pmatrix}
\color{blue}c_{1} \\
\color{blue}c_{2} 
\end{pmatrix}$$
Nun muss die Determinante der Koeffizientenmatrix bestimmt werde: $det(a,b)$

Nun wird die Determinante $Dx = det(c,b)$ bestimmt und die Determinante $Dy = det(a,c)$.

Nun können x und y bestimmt werden:
$$x=\frac{Dx}{det(a,b)} = \frac{det(c,b)}{det(a,b)}$$
$$
y = \frac{Dy}{\det(a,b)} = \frac{\det(a,c)}{\det(a,b)}
$$


## Cramersche Regel 2x2
Hier wird genau gelich vorgegangen wie bei 2x2:
$$
D= \det(a,b,c)
$$
Lösungsvektor  $\vec{d} =\begin{pmatrix}d_{1}\\ d_{2} \\ d_{3}\end{pmatrix}$.

$$
x = \frac{Dx}{D} = \frac{\det(d,b,c)}{D}
$$
$$
y = \frac{Dy}{D} = \frac{\det(a,d,c)}{D}
$$
$$
z = \frac{Dz}{D} = \frac{\det(a,b,d)}{D}
$$
Hier muss die Determinante jedoch mit der [[Regel von Sarrus]] bestimmt werden.