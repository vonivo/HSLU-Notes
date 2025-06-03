Wenn eine [[Zufallsvariable]] $X$ **diskret uniform** verteilt ist schreiben wir:
$$
X\sim \mathsf{dUni}(\text{low},\text{high})\;.
$$
```python
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
from scipy.stats import randint # <---- Verteil-Funktion

x = np.linspace(0.9,6.1,200)
#Random Variable - Parameter low und high: Werte von low bis zu high (excludiert)
X = randint(low=1,high=7)
#Cumulative Distribution Function => Summenhäufigkeit
X_cdf = X.cdf(x)
#Probability Mass Function  => relative Häuffigkeit
X_pmf = X.pmf(np.array([1,2,3,4,5,6]))
sample = X.rvs(size=5000)
fig = plt.figure(figsize=(10,5))
ax1 = fig.add_subplot(1,2,1)
ax1 = plt.plot(x,X_cdf,lw=3)
ax1 = plt.ylim(0,1.02)
ax1 = plt.hlines(0.75,0.9,6.1,color="red",linestyle="dashed")
ax2 = fig.add_subplot(1,2,2)
ax2 = sns.histplot(sample,bins=np.arange(0.5,7.5),stat="density",color="lightblue")
ax2 = plt.vlines(np.array([1,2,3,4,5,6]),0,X_pmf,lw=3)
ax2 = plt.ylim(0,1.02)
plt.show()
#Percent Point Function: 
print(X.ppf(0.75))
print(X.mean())
print(X.var())
print(X.std())
```
![[diskrete_uniforme_verteilung.png]]
