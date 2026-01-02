**Entscheidungsvariablen**
- Für alle Felder $(i,j), i=0,\dots,8;j=0,\dots,8$ sei Variable $x_{i,j}$ die Zahl im Feld $(i,j)$ (Zahl zwischen 1 und 9)

**Bedingungen**
1. Fix Werte: $x_{2,4}=8$
2. Für jede Reihe: $\text{allDifferent}(x_{i,0},x_{i,1},\dots,x_{i,8})$
3. Für jede Kolonne: $\text{allDifferent}(x_{0,j},x_{1,j},\dots,x_{8,j})$
4. Für $i=0,3,6$ und $j=0,3,6$ $\text{allDifferent}(x_{i,j},x_{i,j+1},x_{i,j+2}+ x_{i+1,j},x_{i+1,j+1},x_{i+1,j+2} + x_{i+2,j},x_{i+2,j+1},x_{i+2,j+2})$

**Code**
![[CP_Sudoku_Code.png]]