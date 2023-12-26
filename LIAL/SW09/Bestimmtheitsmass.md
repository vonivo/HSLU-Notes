Das Bestimmtheitsmass bestimmt, wie genau gut der lineare Zusammenhang zwischen Einfluss- und Zielgrösse ist. Man kann somit bestimmen wie genau das [[Lineare Regression|lineare Regressionsmodell]] ist.

![[LIAL/SW09/img/Bestimmtheitsmass.png]]

### SQT
$\color{red}Summe\space der\space Quadrate\space der\space Totalen\space Abweichung$
$$
\sum_{i=1}^{m}(y_{i}-\overline{y})^2 = (y-\overline{y})^T(y-\overline{y})=\color{red} y^TMy
$$

### SQE
$\color{green}Summe\space der\space Quadrate\space der\space erklärten\space Abweichung$ 
$$
\sum_{i=1}^{m}(\hat{y}_{i}-\overline{y})^2 = (\hat{y}-\overline{y})^T(\hat{y}-\overline{y})
$$
Oder: 
$$
SQT - SQR
$$

### SQR
$\color{blue}Summe\space der\space Quadrate\space der\space Restabweichungen\space (Residuen)$ 
$$
\sum_{i=1}^{m}(y_{i}-\hat{y}_{i})^2 = (y - \hat{y})^T(y-\hat{y}) =\color{blue} y^TQy
$$


![[Bestimmtheitsmass 1.png]]

Nun gilt:
$$
R^2 = \frac{\color{green}SQE}{\color{red}SQT}=\frac{\color{red}SQT -\color{blue}SQR}{\color{red}SQT} = 1-\frac{\color{blue}SQR}{\color{red}SQT}
$$
wobie:
$$
\overline{y} = \frac{1}{m}\sum_{i=1}^m y_{i}
$$
Als $\overline{y}$ ist eine [[Zentrierende Matrix]]

Mithilfe der [[Orthogonale Projektionen|Projektionsmatirx]] $P$, der [[Residualmatrix]] $Q$ und der [[Zentrierende Matrix| zentrierenden Matrix]] $M$ lässt sich das alles noch vereinfachen.
$$
R^21-\frac{\color{blue}SQR}{\color{red}SQT} = 1- \frac{y^TQy}{y^TMy}
$$
