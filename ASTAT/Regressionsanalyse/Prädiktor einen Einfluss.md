Der $p$**-Wert** in einer [[Regressionsanalyse]] gibt an, ob ein _**beobachteter Regressionskoeffizient**_ rein zufällig entstanden sein könnte. 

Wir machen also einen [[Hypothesentest]] unter der Annahme, dass kein echter _**Zusammenhang zwischen dem Prädiktor und der Zielvariablen**_ besteht:

- [[Hypothese#Nullhypothese|Nullhypothese]] für das Gewicht $a$ ist $H_{0}:a=0$
- Alternative Hypothese: $H_{1}a \neq 0$

```python
n_permutations = 1000
coefs = []

for _ in range(n_permutations):
    B_permuted = np.random.permutation(B)
    def RSS(coeffs):
        residuen = B_permuted - model(A,coeffs[0],coeffs[1])
        return (residuen**2).sum()
    
    fit_permuted = minimize(RSS, x0=np.zeros(2))
    coefs.append(fit_permuted.x[0])

# p-Wert berechnen (zweiseitig)
coefs = np.array(coefs)
p_value = 100 * np.mean(np.abs(coefs) >= np.abs(fit.x[0]))

> Beobachteter Koeffizient: 0.7141
  Resampling-basierter p-Wert: 0.0
```