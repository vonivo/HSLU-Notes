Geben ist eine quadratische Matrix A. Es wird ein Vektor $\vec{x}$ gesucht, welcher verschiedene vom Null-Vektor ist und bei einer Multiplikation mit a ein Vielfaches von sich selbst ergibt.
$$
Ax = \lambda x
$$
Dieser Vektor $\vec{x}$ heisst **[[Vektoren||Eigenvektor]]** und das dazugehörige $\lambda$ heisst **Eigenwert**.

Um die Eigenwerte und dazugehörigen Eigenvektor zu berechnen, heisst nichttriviale Lösungen von $(A-\lambda I)x = 0$ zu bestimmen. Dies geschieht in zwei Schritten.

## Eigenwerte
Die Eigenwerte sind Lösungen der **charakteristischen Gleichung**.
Um die Charakteristische Gelichung zu erstellen wird das **charakteristische Polynom** benötigt.

### Charakteristisches Polynom
Das charakteristische Polynom ist die [[Determinante]] von $(A-\lambda I)$.
$$
\det(A-\lambda I)
$$
### Charakterisitsche Gleichung
Aus dem charakteristischen Polynom wird die charakteristische Gleichung, indem man das Polynom gleich $0$ setzt.
$$
\det(A-\lambda I) = 0
$$

Falls A eine $n \times n$-[[Matrizen|Matrix]] ist, dann ist die charakteristische Gleichung eine Gleichung $n$-ten Grades.

## Eigenvektoren
Zu den Eigenwerten $\lambda_i$ bestimmen, wird die nichttriviale Lösung des homogenen [[Lineare Gleichungsysteme|lineare Gleichungssystem]]:
$$
(A-\lambda_{i}I)x = 0
$$
Die Lösung $x_i \ne 0$ ist der zum Eigenwert $\lambda_i$ gehörende Eigenvektor.

## Eigenschaften
- Die Eigenvektoren $x_1, x_2$ zu verschiedenen Eigenwerten $\lambda_1,\lambda_2 \space (\lambda_1 \ne \lambda_2)$ sind linear unabhängig.,
Eigenschaften einer $n \times n$-Matrix:
- Die [[Determinante]] einer [[Matrizen|Matrix]] ist gleich dem Produkt der Eigenwerte der Matrix:
$$
\det(A) = \prod_{i=1}^n\lambda _{i}
$$
- Die [[Spur einer Matrix|Spur]] der Matrix ist gleich der Summe der Eigenwerte der Matrix:
$$
\operatorname{spur}(A) = \sum_{i=1}^n\lambda _{i}
$$





#charakteristischeGleichung
#charakteristischePolynom