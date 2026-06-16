>[!Definition]
>Ein Maschinensprachprogramm ist eine Reihe von kodierten Anweisungen. Eine typische Anweisung in einem 16-Bit-Computer kann etwa `1010 0011 0001 1001` bzw. `ADD R3, R1, R9` lauten.

**Arithmetische und logische Operationen**
Jeder Computer muss die grundlegenden arithmetischen Operationen wie Addition, Subtraktion sowie grundlegende boolesche Operationen wie bitweise Negation, Bitshift usw. ausführen können.
- `ADD R2, R1, R2`  <- R2 = R1 + R3
- `AND R1, R1, R2` <- R1 = R1 & R2

**Speicherzugriff**
Speicherzugriff kann auf drei verschiedene Arten erfolgen:
1. **Direkte Adressierung**:
	`LOAD R1, 67` <- R1 = Memory\[67]
2. **Unmittelbare Adressierung**:
	`LOADI R1, 67` <- R1 = 67
3. **Indirekte Adressierung**
	`x = foo[j]` oder `x =*(foo+j)`
	`ADD R1, foo, j` <- R1 = foo+j
	`LOAD* R2, R1`    <-  R2 = Memory\[R1]
	`STR R2, x`          <- x = R2


**Kontrollfluss**
Damit der Kontrollfluss des Programms gesteuert werden kann, benötigt es Verzweigungen zu anderen Befehlen. Dadurch werden:
- Wiederholungen
- Bedingte Ausführungen
- Aufrufe eines Unterprogramms
möglich.

**Beispiel:**
```java
while (R1 >= 0) {
	// code segemnt 1
}
// code segment 2
```
wird z.B. zu:
```
beginWhile:
JNG R1, endWhile        // Wenn R1 <0 gehe zu endWhile
	# Code Segment1
JMP beginWhile
endWhile:
# code segment 2
```

