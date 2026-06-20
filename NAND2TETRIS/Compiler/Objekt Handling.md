Das Objekthandling in Jack wird anhand einer Analogie zu Structs in C beschreiben.
![[Pasted image 20260620111647.png|240]]
In RAM liegt ein Struct mit zwei Werten `11` und `7` die Basisadresse des Structs ist `9543`.

## Erstellung eines neuen Struct
```
push constant 2      // ein struct mit 2 feldern
call Memory.alloc 2
pop pointer 0        // lade die Baseadresse in THIS-Segment

push constant 11     // befülle das Struct über this + feld offset
pop this 0

push constant 7
pop this 1

push pointer 0       // speicher die basisadresse in eine variable
pop local 0
```

## Manipulieren eines Structs
```
push local 1
pop pointer 0        // befülle THIS mit der basisadresse

push constant 5
pop this 0           // bearbeiten des Struct

push constant 3
pop this 1
```
