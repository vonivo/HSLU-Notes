**Caller**
- `p1` und `p2` sind deklariert und konstruiert
- `d` ist deklariert
```java
let d = p1.distance(p2)
```
wird zu:
 ```
 push local 0           // local 0 -> p1
 push local 1           // local 1 -> p2      
 call Point.distance 2   
 pop local 2            // local 2 -> d                   
 ```
 - Das Objekt auf welchem die Methode ausgeführt wird, hier `p1` wird als 1. Parameter mitgegeben.

**Callee**
```java
...
method int distance(Point other) {
	var int dx,dy;
	let dx = x - other.getx();
	let dy = y - other.gety();
	return Math.sqrt((dx*dx) + (dy*dy))
}
...
```
wird zu
```
function Point.distance 2
push argument 0         
pop pointer 0          // THIS korrekt setzen

// Rest der Methode
push this 0
push argument 1
call Point.getx 1
sub
pop local 0

...

add
call Math.sqrt 1
return
```

>[!Error]
>**Wichtig:** Der Compiler fügt der [[Symboltable]] der Methode noch einen eintrag
>`this Point argumnet 0` hinzu.