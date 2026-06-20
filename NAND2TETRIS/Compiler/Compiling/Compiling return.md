Die Return expression ist extrem einfach zu kompilieren.

**Mit Rückgabewert**
`return expression` wird zu:
```
// VM-Code durch compileExpression generiert
return
```
Auch hier liegt der interessante Wert wieder durch [[Compiling Expressions]] oben auf dem Stack.

**Ohne Rückgabewert**
`return;` wird zu 
```
push constant 0
return
```


- Jack-Funktionen müssen immer mit einem `return` enden.

**Pseudocode**
![[Pasted image 20260620110927.png|314]]oder mit `push constant 0` 