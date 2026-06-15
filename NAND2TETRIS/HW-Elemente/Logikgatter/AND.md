![[Pasted image 20260615133907.png]]

|               |                                         |
| ------------- | --------------------------------------- |
| **Chipnanme** | AND                                     |
| **Eingänge**  | a,b                                     |
| **Ausgägne**  | out                                     |
| **Funktion**  | Wenn $a=b=1$ dann $out=1$ sonst $out=0$ |

**Konsturution**
![[Pasted image 20260615134022.png]]
2 sequenziell geschaltete [[NAND]].

**Wahrheitstabelle**

| a   | b   | out |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 0   |
### And16
|               |                                            |
| ------------- | ------------------------------------------ |
| **Chipnanme** | And16                                      |
| **Eingänge**  | a\[16], b\[16]                             |
| **Ausgägne**  | out\[16]                                   |
| **Funktion**  | Für $i=0\dots 15$ $out[i]=AND(a[i], b[i])$ |
