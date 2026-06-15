Zwei Binärzahlen können Ziffer für Ziffer von rechts nach links addiert werden:
![[Pasted image 20260615145458.png]]
Diese Addition kann aus logischen Gattern aufgebaut werden.

Ein Binärsystem mit $n$ Ziffern kann eine Menge von $2^{n}$ verschiedenen Bitmustern erzeugen.


**2er Komplement**
Damit der Computer auch direkt mit negativen Zahlen rechnen kann, wird das 2er-Komplement verwendet:
>[!Definition]
>2er-Komplement von $x=\begin{cases} 2^{n}-x& \text{ wenn }x \neq 0 \\ 0, &sonst \end{cases}$

**Beispiel:**
In einem 5-Bit Binärsystem ist 2er-Komplement-Darstellung von $-2$ oder $minus(00010)_{b}$
$$
2^{5}-(00010)_{b}=(32)_{d}-(2)_{d}=(30)_{d}=(11110)_{d}
$$
![[Pasted image 20260615150112.png]]

### Eigenschaften
- Das System kann insgesamt $2^{n}$ vozeichnebehaftete Zahlen kodieren, von denen die Maximal- und Minimalzahlen $2^{n-1}-1$ bzw. $-2^{n-1}$ sind.
- Die Codes aller positiven Zahlen beginnen mit einer $0$
- Die Codes aller negativen Zahlen beginnen mt einer $1$
- Um den Code von $-x$ aus dem Code von $x$ zu erhalten, lässt man alle hinteren (niedrigstwertigen Nullen) und die erste niedristwertige Eins stehen und dreht dann alle übrigen B
- Die Addition in dieser Darstellung funktioniert OOTB -> dadurch wird die HW-Kmplexität reduziert.


