## Konstruktion
- Arrays sind Instanzen der OS-Klasse [[Array]].
- Um ein Array zu erstellen, wird `Array.new` aufgerufen.
![[Pasted image 20260620123254.png]]
- Wird durch [[Compiling Let]] abgedeckt.


## Access
Für den Array-Access wird das `THAT`-Segement benutzt. In diesem Segment wird direkt die richtige Adresse berechnet.

**Einfaches Beispiel**

```
// let arr[2] = x

// array adresse berechnen und in THAT speichern
push arr
push 2
add
pop pointer 1

push x
pop that 0

// let x = arr[2]
push arr
push 2
add
pop pointer 1

push that 0
pop x
```

Obiges Beispiel funktioniert bei einfachen Arrays, wenn Array-Operationen verschachtelt sind, funktioniert es jedoch nicht, da der `THAT`-Pointer überschrieben wird. (z.B. bei `let arr[i] = b[j]`)

**Allgemeinter VM-Code**
```
// let a[i] = b[j]

push a
push i
add
push b
push j
add
pop pointer 1         // THAT = address of b[j]
push that 0           // statck top = b[j]
pop temp 0            // temp 0 = b[j]
pop pointer 1         // THAT = addres of a[i]
push temp 0           // stack top = b[j]
pop that 0            // a[i] = b[j]
```

**Pseudocode**
![[Pasted image 20260620124234.png]]