![[Pasted image 20260615133615.png]]

|               |                                         |
| ------------- | --------------------------------------- |
| **Chipnanme** | NOT                                     |
| **Eingänge**  | in                                      |
| **Ausgägne**  | out                                     |
| **Funktion**  | Wenn $in=0$ dann $out =1$ sonst $out=0$ |

**Konsturution**
![[Pasted image 20260615133750.png]]
[[NAND]] mit beiden eingängen welche von $in$ bedient werden.

**Wahrheitstabelle**

| in  | out |
| --- | --- |
| 0   | 1   |
| 1   | 0   |

### Not16
|               |                                       |
| ------------- | ------------------------------------- |
| **Chipnanme** | Not16                                 |
| **Eingänge**  | in\[16]                               |
| **Ausgägne**  | out\[16]                              |
| **Funktion**  | Für $i=0\dots 15$ $out[i]=Not(in[i])$ |
