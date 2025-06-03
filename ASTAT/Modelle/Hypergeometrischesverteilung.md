Wenn ein *diskrete* Zufallsvariable $X$ **Hypergeometrisch** verteilt ist, schreiben wir 
$$
X\sim \mathsf{HypG}(M,n,N)\;.
$$

| Parameter | Beschreibung                                  |
| --------- | --------------------------------------------- |
| M         | Anzahl aller Teile in einem Behälter          |
| n         | Anzahl aller defekten Teile in einem Behälter |
| N         | Anzahl wie viele Teile gezogen werden         |

```python
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
from scipy.stats import hypergeom

x = np.arange(0,5)
#Random Variable - Parameter M, n und N: n von M Kugeln, mit N von der Sorte 1
X = hypergeom(M=20,n=4,N=8)
#Cumulative Distribution Function => relative Summenhäufigkeit
X_cdf = X.cdf(x)
#Probability Mass Function => relative Häufigkeit
X_pmf = X.pmf(np.array([0,1,2,3,4]))
#
sample = X.rvs(size=5000)
fig = plt.figure(figsize=(10,5))
ax1 = fig.add_subplot(1,2,1)
ax1 = plt.stairs(X_cdf,orientation="vertical",lw=3)
ax1 = plt.ylim(0,1.02)
ax1 = plt.xlim(-0.1,4.1)
ax1 = plt.hlines(0.75,-0.1,4.1,color="red",linestyle="dashed")
ax2 = fig.add_subplot(1,2,2)
ax2 = sns.histplot(sample,bins=np.arange(-0.5,5.5),stat="density",color="lightblue")
ax2 = plt.vlines(np.array([0,1,2,3,4]),0,X_pmf,lw=3)
ax2 = plt.ylim(0,1.02)
plt.show()
#Percent Point Function: 
print(X.ppf(0.75))
print(X.mean())
print(X.var())
print(X.std())
```
![[hypergeometrische_verteilung.png]]