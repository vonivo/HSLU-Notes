Wir betrachten die [[Reellwertige Funktion|reellwertige Funktion]] $f$, welche von zwei Variablen abhängt.
Wir betrachten die Ebene $y=y_{0}$ für eine Konstante $y_{0}$. Dann hängt die Funktion
$$
g(x)=f(x,y_{0})
$$
nur noch von der Variable $x$ ab.
Diese Methode kann nun nach $x$ [[Ableitung|abgeleitet]] werden. Das Resultat ist die **partielle Ableitung vom $f$ nach $x$**
$$
g'(x) = f_{x}(x,y_{0})=\left.\frac{\partial f(x,y)}{\partial x}\right|_{x,y=y_{0}}
$$
an der Stelle $(x,y=y_{0})$.
Hier bezeichnet $f_{x}$, oder $\frac{\partial f(x,y)}{\partial x}$, die partielle Ableitung von $f$ nach der Variable $x$.

Das ganze funktioniert analog mit einer [[Ableitung]] nach $y$. Dabei muss einfach $x=x_{0}$ als konstant gesetzt werden.


Die **partiellen Ableitungen** von $f$ nach $x$ an der Stelle $(x_{0}, y_{0})$ sind nach dem oben gesagten wie folgt definiert:
$$
\left.\frac{\partial f}{x}\right|_{(x_{0},y_{0})}\equiv f_{x}(x_{0}, y_{0}) = \lim_{ h \to 0 } \left( \frac{f(x_{0}+h,y_{0})-f(x_{0},y_{0})}{h} \right)
$$
	Die [[Ableitung]] nach $x$ gibt die Änderungsrate von $f$ bezüglich $x$ in $x_{0},y_{0}$ an

$$
\left.\frac{\partial f}{y}\right|_{(x_{0},y_{0})}\equiv f_{y}(x_{0}, y_{0}) = \lim_{ h \to 0 } \left( \frac{f(x_{0},y_{0}+h)-f(x_{0},y_{0})}{h} \right)
$$
	Die [[Ableitung]] nach $y$ gibt die Änderungsrate von $f$ bezüglich $y$ in $x_{0},y_{0}$ an

Fasst man $x_{0}$ und $y_{0}$ wieder als Variablen auf, erhält man **partielle Ableitungsfunktionen** $f_{x}(x,y)$ und $f_{y}(x,y)$. Oft verwendet man mit $z=f(x,y)$ alternative Bezeichnungen
$$
f_{x}(x,y)= \frac{\partial z}{x} \space\space\space\space\text{und }\space\space f_{y}(x,y)= \frac{\partial z}{y}
$$
$$
f_{x}(x,y)= \left.\frac{\partial z}{x}\right|_{(x_{0},y_{0})} \space\space\space\space\text{und }\space\space f_{y}(x,y)=\left. \frac{\partial z}{y}\right|_{(x_{0,}y_{0})} 
$$
## Beispiel
Sei $f(x,y)=\frac{x^{2}}{y+1}$. Gesuch ist $f_{x}(3,2)$.

Wir setzen $y=2$ und leiten ab
$$
\begin{align}
\frac{\partial f}{x}&=\frac{(x^{2})'}{2+1} \\
&=\frac{2x}{3}
\end{align}
$$
So erhalten wir für $x=3$ $\frac{2\cdot3}{3}=2$.


Bestimme die partiellen Ableitungen von $f(x,y)=y^{2}e^{3x}$:
$$
\begin{align}
\frac{\partial f}{x}&=y^{2}\left(e^{ 3x }\right)' \\
&=3y^{2}e^{ 3x }
\end{align}
$$
$$
\begin{align}
\frac{\partial f}{y}&=\left(y^{2}\right)'e^{ 3x } \\
&=2ye^{ 3x }
\end{align}
$$