>[!info]
>Die Big-O-Notation ist eine form der Notation der **Ordnung** eines [[Algorithmus]] bezüglich seiner [[AD/Algorithmen/Komplexität]].

## Beispiel
Die Ordnung $O(n^{2})$ bedeutet, dass:
- **Verdoppelung** von n
	$2^{2}$ = 4-Fache Rechenzeit
	$$
\frac{({\color{red}2} n)^{2}}{(n)^{2}} = 4
$$
- **Verdreifachung** von n
	$2^{3}$ = 9-Fache Rechenzeit
		$$
\frac{({\color{red}3} n)^{2}}{(n)^{2}} = 9
$$
- **Verzehnfachung** von n
	$2^{10}$ = 100-Fache Rechenzeit
		$$
\frac{({\color{red}10} n)^{2}}{(n)^{2}} = 100
$$

## Definition
Die **Big-O-Notation** birngt zum Ausdruck, dass eine Funktion f(n) **höchstens** so schnell wächst wie eine andere Funktion g(n).
**g(n) ist die obere Schranke für f(n)**


## Wichtige Ordnungsfunktionen

| Name          | Ordnung      | Anwendung         |
| ------------- | ------------ | ----------------- |
| Konstant      | $O(1)$       | Hasing            |
| Logarithmisch | $O(ln(n))$   | binäres Suchen    |
| Linear        | $O(n)$       | Suchen im Text    |
| n log n       | $O(n*ln(n))$ | Sortieren         |
| Polynomial    | $O(n^{m})$   | simples Sortieren |
| Exponential   | $O(d^{n})$   | Optimierungen     |
| Fakultät      | $O(n!)$      | Permutationen     |
In der Praxis haben [[Algorithmus|Algorithmen]] typisch maximal die Ordnung $n^{2}$ oder $n^{3}$.
![[Funktionsverläufe.png]]

## Rechenregeln
- f(n) = $0.0001\times n^{3}$ -> $O(n^{3})$
	Konstante Faktoren ignorieren
- f(n) = $Id(100\times n)$ -> $O(Id(n)) = O(\log_{10}(n)) = O(\ln(n))$
	Basis des Logarithmus spielt keine Rolle.
- f(n) = $2+37n^{3}+0.1n^{4}+0.0001\times2^{n}$ = $O(2^{n})$
	Nur stärkster Summand zählt