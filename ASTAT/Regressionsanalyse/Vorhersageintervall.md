**Vorersageintervall** quantifiziert, die **Unsicherheit** der Prognose durch eine [[Regressionsanalyse]].

- Im Gegensatz zum [[Intervallschätzungen|Konfidenzintervall]], berücksichtigt das Vorhersageintervall zusätzlich die zufällige Streuung neuer Beobachtungen um diesen Mittelwert.
- Ein **95%-Vorhersageintervall** gibt an, dass in 95% der Fälle der tatsächliche Wert der Zielvariable einer neuen Beobachtung innerhalb des angegebenen Intervalls liegen wird – vorausgesetzt, das Modell ist korrekt spezifiziert.

Das Vorhersageintervall umfasst die **Unsicherheit der Modellschätzung** sowie die **natürliche Streuun neuer Datenpunkte** und ist deshabl breiter als ein Konfidenzintervall.

```python
a_new = 5.86
b_predict = model(a_new, fit.x[0], fit.x[1])

n_bootstrap = 1000
predictions = []

for _ in range(n_bootstrap):
    indices = np.random.choice(n, n, replace=True)
    A_sample = A[indices]
    B_sample = B[indices]
    def RSS(coeffs):
        residuen = B_sample - model(A_sample,coeffs[0],coeffs[1])
        return (residuen**2).sum()
    fit_permuted = minimize(RSS, x0=np.zeros(2))
    
    # Vorhersage inkl. zufälligem Fehler (residuenbasiert)
    b_pred = model(a_new,fit_permuted.x[0],fit_permuted.x[1])
    
    # Schätzfehler aus Residuen
    residuals = B_sample - model(A_sample,fit_permuted.x[0],
								    fit_permuted.x[1])
    error = np.random.choice(residuals) # Zufälliges wählen eines 
                                        # Fehlers
    b_pred_with_noise = b_pred + error

    predictions.append(b_pred_with_noise)

# 95%-Vorhersageintervall
lower = np.percentile(predictions, 2.5)
upper = np.percentile(predictions, 97.5)
```
