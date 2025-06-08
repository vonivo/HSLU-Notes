## Standardfehler
### Einfache Regression
Um ein Modell einer [[Regressionsanalyse]] zu bewerten, wird der Standardfehler der Residuen berechnet:
$$
RSE = \sqrt{ \frac{RSS}{n-2} }=\sqrt{ \frac{r_{1}^{2}+r_{2}^{2}+\dots+r_{n}^{2} }{n-2}}
$$
**$RSE$** ist ein Gütemass für ein angepasstes Regressionsmodell.

```python
RSE = np.sqrt(1/(df.shape[0]-2) * ((B-model(A, fit.x[0], 
										fit.x[1]))**2).sum())
RSE = np.sqrt(fit.fun/(df.shape[0]-2))
```

## [[Multiple Regressionsanalyse]]
Um ein Modell einer [[Multiple Regressionsanalyse|multiplen Regressionsanalyse]] zu bewerten, wird der Standardfehler der Residuen berechnet. Zusätzlich werden die Anzahl **Präditoren $p$** miteinbezogen:
$$
RSE=\sqrt{ \frac{RSS}{n-p-1} }
$$
### Bestimmtheitsmass
Das Bestimmtheitsmass:
$$
R^{2}=\frac{MQD\{predict(x_{1}), predict(x_{2}), \dots, predict(x_{n})\}}{MQD\{y_{1},y_{2},\dots y_{n}\}})
$$
gibt an, welcher **Bruchteil der mittleren quadratischen Abweichung** das Modell erklären kann.
Es gilt $0\leq R^{2} \leq 1$.

Für **lineare Modelle** gilt $R^{2}=^{2}$ zwischen dem Bestimmtheitsmass $R^{2}$ und dem [[Kovarianz#Korrelationskoeffizient|Korrelationskoeffizient]] $r$.

```python
R_squared = predict(A).var() / B.var()
R_squared = pd.DataFrame({"A":A,"B":B}).corr().loc["A","B"]**2
