Wenn ein *stetige* Zufallsvariable $X$ **Expenential** verteilt ist, schreiben wir 
$$
X\sim \mathsf{Exp}(\text{loc},\text{scale})\;.
$$
```python
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
from scipy.stats import expon

x = np.linspace(-0.1,15.1,200)
#Random Variable - Parameter loc und scale: Erwartungswert scale und Startwert loc
X = expon(loc=1,scale=2)
#Cumulative Distribution Function
X_cdf = X.cdf(x)
#Probability Density Function
X_pdf = X.pdf(x)
#
sample = X.rvs(size=5000)
fig = plt.figure(figsize=(10,5))
ax1 = fig.add_subplot(1,2,1)
ax1 = plt.plot(x,X_cdf,lw=3)
ax1 = plt.ylim(0,1.02)
ax1 = plt.hlines(0.75,-0.1,15.1,color="red",linestyle="dashed")
ax2 = fig.add_subplot(1,2,2)
ax2 = sns.histplot(sample,stat="density",color="lightblue")
ax2 = plt.plot(x,X_pdf,lw=3)
ax2 = plt.ylim(0,1.02)
plt.show()
#Percent Point Function: 
print(X.ppf(0.75))
print(X.mean())
print(X.var())
print(X.std())
```

![[exponential_verteilung.png]]