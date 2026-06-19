**Arithmetische Befehle**

| Befehl | Berechnung | Kommentar                                   |
| ------ | ---------- | ------------------------------------------- |
| add    | x + y      | Ganzzahlige Addition im Zweierkomplement    |
| sub    | x - y      | Ganzzahlige Subtraktion im Zweierkomplement |
| neg    | -y         | Arithmetische Negation im Zweierkomplement  |

```
// add / subb
@SP  
AM=M-1      // SP-- und speichere in A und M
D=M         // lade nun M[SP] in D

A=A-1       // Setze A auf das 1. Arugment
M=M+D       // Berechne

// neg
@SP
A=M-1
M=-M
```

**Verleisbefehel**

| Befehl | Berechnung | Kommentar            |
| ------ | ---------- | -------------------- |
| eq     | x==y       | Gleichheitsrelation  |
| gt     | x > y      | Grösser als Relation |
| lt     | x < y      | Kleiner als Relation |

```
// gt, lt, eq
@SP  
AM=M-1      
D=M         

A=A-1       
D=M-D       

@GT_TURE
D;JGT

// FALSE
@SP
A=M-1
M=0

@GT_END  
0;JMP

(GT_TRUE)  
// TRUE  
@SP  
A=M-1  
M=-1  
  
(GT_END)
```

**Logsiche Befehel**

| Befehl | Berechnung | Kommentar       |
| ------ | ---------- | --------------- |
| and    | x and y    | Bitweises Und   |
| or     | x or y     | Bitweises Oder  |
| not    | not y      | Bitweises Nicht |
```
// and,OR
@SP
AM=M-1   // SP--
D=M      // Operand a in D

A=A-1
M=M&D


// NOT
@SP
A=M-1   // SP--
M=!M     
```