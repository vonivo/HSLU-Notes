**Caller**
Der Caller-Code wird komplett normal eine normale Expression welche mit [[Compiling Let]] und [[Compiling Expressions]] kompiliert wird gehandelt:
![[Pasted image 20260620112237.png]]

**Callee**
![[Pasted image 20260620112544.png]]
1. Lege die Anazhl an Felder auf den Stack `push constant 2`
2. Alloziere Memory für die Felder `call Memory.alloc 1`
3. Speichere die Basisadress von `alloc` in `THIS` mit `pop pointer 0`
4. Normale Kompilation
5. Kompiliere die `return`-Anweisung.
