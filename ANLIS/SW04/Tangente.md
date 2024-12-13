Eine Tangente ist eine Gerade, welche eine [[ANLIS/SW01/Funktionen/Funktion]] genau in einem Punkt berührt.
![[Tangente.png]]

## Tangentengleichung
Um die Gleichung der Tangente am Punkt $x_{0}$ zu bekommen, muss zuerst mit der [[Ableitung]] die Steigung an diesem Punkt berechnet werden:
$$
m= f'(x_{0})
$$
nun kann mit der Steigung und der [[Lineare Funktion|Punkt-Richtungsform]] die Gerade bestimmt werden.
$$
\begin{align}
m = \frac{\Delta y}{\Delta x}=f'(x_{0})&=\frac{y-f(x_{0})}{x-x_{0}} \\
y-f(x_{0})&=f'(x_{0})(x-x_{0}) \\
y&=f(x_{0})+f'(x_{_{0}})(x-x_{0})
\end{align}
$$
Dieser Vorgang stellt eine Approximation (Annäherung) der [[ANLIS/SW01/Funktionen/Funktion]] $f(x)$ durch eine [[Lineare Funktion]] dar und **Linearisierung von $f$ in $x_{0}$** bezeichnet.
#linearisierung
Die Linearisierung ist im Punkt $x_{0}$ exakt, wird aber je weiter entfernt von $x_{0}$ ungenauer.
