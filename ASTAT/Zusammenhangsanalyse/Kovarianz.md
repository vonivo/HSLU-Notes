Die grundlegende Metrik der [[Korrelation|Korrelationsanalyse]] für zwei [[Statistisches Merkmal|metrische Merkmale]] $A$ und $B$ ist die **Kovarianz**.
$$
\sigma_{ab}=\frac{1}{n}\big((x_1-\bar{x})\cdot(y_1-\bar{y})+(x_2-\bar{x})\cdot(y_2-\bar{y})+\ldots+(x_n-\bar{x})\cdot(y_n-\bar{y})\big)
$$

Im Gegensatz zur [[Streumass|Varianz]] kann die Kovarianz auch negative Werte annehmen.
Das Vorzeichen gibt aufschluss über die Richtung ds Zusammenhangs:
- Wenn die **Kovarianz** $\pmb{\sigma_{ab}}$ **positiv** ist, gibt es eine **positive [[Korrelation]]**.
- Wenn die **Kovarianz** $\pmb{\sigma_{ab}}$ **negativ** ist, gibt es eine **negative [[Korrelation]]**.
- Wenn die **Kovarianz** $\pmb{\sigma_{ab}}$ **Null** ist, gibt es keine **Korrelation**.

>[!info]
>Wird die Kovarianz für das Merkmal $A$ mit sich selbst berechnet enthält man die Varianz:
>$$
\sigma_{aa}=\frac{1}{n}\big((a_1-\bar{a})\cdot(a_1-\bar{a})+(a_2-\bar{a})\cdot(a_2-\bar{a})+\ldots+(a_n-\bar{a})\cdot(a_n-\bar{a})\big)
>$$

## Kovarianz mit Python berechnen
```python
df_p.cov(ddof=0)         # =1 wird bei stichproben gemacht, es wird 
						 # noch durch 1/n dividiert um ein 
						 # erwartungstreuer schätzer zu haben
> Kovarianzmatrix:
>           A          B
>A  19.668928  14.523421
>B  14.523421  12.944763
```

## Korrelationskoeffizient
Der absolute Zahlenwert der Kovarianz kann aufgrund der hohen Dimensionen und der fehlenden Skala schlecht eingeschätzt werden. Daher existiert der **Korrelationskoeffizient:**
$$
r=\frac{\sigma_{ab}}{\sigma _{a}\cdot \sigma_{b}}
$$
- $\sigma_{ab} \to$ Kovarianz
- $\sigma_{a}$/$\sigma_{b} \to$ [[Streumass|Standardabweichung]]

Diese Normierung bewirkt, dass der Korrelationskoeffizient **dimensionslos** ist und darüber hinaus gilt $-1 \leq r\leq 1$.

>[!error]
>Der **Korrelationskoeffizient** beschreibt nur muss linearität