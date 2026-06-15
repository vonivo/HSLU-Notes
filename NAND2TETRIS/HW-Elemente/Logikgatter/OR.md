![[Pasted image 20260615134102.png]]

|               |                                         |
| ------------- | --------------------------------------- |
| **Chipnanme** | OR                                      |
| **Eingänge**  | a,b                                     |
| **Ausgägne**  | out                                     |
| **Funktion**  | Wenn $a=b=0$ dann $out=0$ sonst $out=1$ |

**Konsturution**
![[Pasted image 20260615134147.png]]

**Wahrheitstabelle**

| a   | b   | out |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 1   |
### Or16

|               |                                           |
| ------------- | ----------------------------------------- |
| **Chipnanme** | Or16                                      |
| **Eingänge**  | a\[16], b\[16]                            |
| **Ausgägne**  | out\[16]                                  |
| **Funktion**  | Für $i=0\dots 15$ $out[i]=OR(a[i], b[i])$ |

### Or8Way
|               |                                       |
| ------------- | ------------------------------------- |
| **Chipnanme** | Or8Way                                |
| **Eingänge**  | in\[8]                                |
| **Ausgägne**  | out                                   |
| **Funktion**  | $out = OR(in[0],in[1], \dots ,in[7])$ |
![[Pasted image 20260615135612.png]]