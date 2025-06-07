>[!Definition]
>Die Regressionsanalyse ist ein zentrales statistisches Verfahren zur Beschreibung von [[Zusammenhangsanalyse|Zusammenhängen]] zwischen [[Statistisches Merkmal|Merkmalen]].
>

Ziel ist es den Einfluss einer oder mehreren unabhängigen Variablen, den **Prädiktoren $x_{1},x_{2},\dots,x_{n}$** auf eine abhängige Variable, der **Zielgrösse** $y$, zu quantifizieren und Vorhersagen zu ermöglichen.
$$
y=predict(x_{1},x_{2},\dots,x_{n})
$$
Die einfachste Form ist die [[Lineare Regression]] bei der eine abhängige Varibale durch genau einen Prädiktor vorhergesagt wird:
$$
y = predict(x) = a \cdot x+b
$$
In viele Anwendungen ist auch die multiple lineare Regression relevant, bei der mehrere Einflussgrössen gleichzeitig berechnet werden:
$$
y=predict(x_{1},x_{2},\dots,x_{n})=a_{1}\cdot x_{1}+a_{2}\cdot x_{2}+\dots+a_{n}\cdot x_{n}+b
$$
Die **Regressionskoeffizienten** $\hat{a}_{1},\hat{a}_{2}, \hat{a}_{n}$ geben an, wie stark sich die Zielvariable verändert, wenn sich ein **Prädiktor** unter Konstanthaltung zu allen anderen Variablen. Daher wird $\hat{a}_{i}$ auch als **Gewicht** des Prädiktor $x_{i}$ genannt.

Neben der Schätzung der Modellparameter erlaubt die Regressionsanalyse auch die **statistische Bewertung der Modellgüte**, die **Signifikanzprüfung einzelner Prädiktoren** und die **Quantifizierung der Vorhersageunsicherheit**


## Koeffiziente finden:
Für alle Datenpunkte werden die Residuen berechnet:
$$
r_{i}=y_{i}-predict(x_{i})=y_{i}-(a\cdot x_{i}+b)
$$
Danach bestimmt man die **Summe der Residuenquadrate RSS**:
$$
RSS=r_{1}^{2}+r_{2}^{2}+\dots+r_{n}^{2}
$$
$a$ und $b$ werden nun so bestimmt, dass $RSS$ minimal ist.
```python
import numpy as np
from scipy import minimize

A = np.array(x1,x2,x3,...,xn)
B = np.array(y1,y2,y3,...,yn)

def model(x,a,b):
	return a*x + b

def RSS(coeffs):
	residuen = B - model(A, coeffs[0], coeffs[2])
	return (residuen**2).sum()

fit = minimize(RSS, x0=np.zeros(2))

> message: Optimization terminated successfully.
  success: True
   status: 0
      fun: 419.1620417846194        -> Minimaler RSS
        x: [ 7.141e-01  2.952e+00]
      nit: 4
      jac: [ 0.000e+00 -3.815e-06]
 hess_inv: [[ 1.433e-04 -1.002e-03]
            [-1.002e-03  9.505e-03]]
     nfev: 18
     njev: 6
```

**Vorhersagen**:
```python
y_preict = model(x, fit.x[0], fit.x[1])
```