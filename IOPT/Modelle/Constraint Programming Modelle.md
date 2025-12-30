Constraint-Progamming Modelle sind:
- Sehr **flexibel**: Alle möglichen mathematischen/logischen Ausdrücke können verwendet werden:
	- $x \neq y$
	- Falls $x>0$, dann $y=2000$
	- $x^{3}(y^{2}+y-200)\geq 49+x^{2}\text{min}(x,y)$
- Daraus entsteht ein **intuitives, kompaktes, lesbares Modell** nahe an der natürlichen Sprache

## Variablen
### Klassische Variablen
- [[Binäre Varialben]]: $x\in\{ 0,1 \}$ entspricht $x\in\{ FALSE, TRUE \}$
```python
y=[model.NewBoolVar('y_{}'.format(j)) for j in range(countS)]
```
- Ganzzahlige Variablen: $x \in \{ a,a+1,\dots,b \}$
```python
x_s=model.NewIntVar(0,100, 'Anzahl Segelboote')
x_m=model.NewIntVar(0,120, 'Anzahl Motorboote')
```
- Kontinuierliche Variablen: $x\in[a,b]$
	- Nicht unterstütz in google OR-Tools
- Spezielle Variablen: $x\in\{ \text{Hund}, \text{Ziege}, \text{Katze} \}$
```python
x1 = model.NewIntVarFromDomain(cp_model.Domain.FromValues([1,3,4,6]), 'x1')
x2 = model.NewIntVarFromDomain(cp_model.Domain.FromIntervals([[1,2],[4,6]]), 'x2')
```
### Speziell strukturierte Variablen
- **Mengenvariablen**: Nimmt eine Menge von Werten als Wert an.
	- Beispiel: Intervallvariable: Nimmt eine Menge von Werten in einem Intervall an (Für Scheduling)
		```python
		duration = 5
		startVar = model.NewIntVar(0,30,'startX')
		endVar = model.NewIntVar(0,30,'endX')
		intervalVar = model.newIntervalVar(startVar, duration, endVar, 'intervalX)
		```

## Bedinungen
- **Algebraische Ausdrücke**
```python
model.Add(8*x_s + 4*x_m <= 1000)
model.Add(x_s != x_m)
```
- **Tabellen Bedingungen**
```python
model.AddAllowedAssignments([x_s,x_m], [(0,0),(1,1),(2,2),(5,2)])
model.AddForbiddenAssignments([x_s,x_m], [(65,120),(66,118),(2,2),(5,2)])
```
- **Variable als Index**
	- $y=\text{gain}[x]$, wobei $x$ und $y$ Variablen und gain eine Liste von Parametern sind.
	- Beispiel: $\text{gain}[1,5,7,10,13,15]$ falls nun $x=3$, dann muss $y=10$ sein. Und falls $y=7$ muss $x=2$ sein.
```python
x = model.NewIntVar(0,10,'x')
val = model.NewIntVar(1,2**10,'val')

precalulated = [2**i for i in range(11)]
model.AddElement(x, precalculated, val)

model.Add(x==4) # => y=16
```
- **Globale Bedingunen**
	- $\text{Alldifferent}(x_{1},x_{2},\dots,x_{n})$
	- etc.

## Zielfunktion
- **Ohne Zielfunktion**: typisches Constraint Problem
- **Mit Zielfunktion**
	- `model.Maximize(2400*x_s + 2000*x_m)`
	- `model.Minimize(sum(x))`
- Finde **eine Lösung**: `solver = cp_model.CpSolver(); solver.Solve(model)`
- Finde **alle Lösungen**: `solution_printer = VarArraySoltuionPrinter(x); status = solver.SearchForAllSolutions(model, solution_printer)`
