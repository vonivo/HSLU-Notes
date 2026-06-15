![[Pasted image 20260615134412.png]]

|               |                                           |
| ------------- | ----------------------------------------- |
| **Chipnanme** | Mux                                       |
| **Eingänge**  | a,b, sel                                  |
| **Ausgägne**  | out                                       |
| **Funktion**  | Wenn $sel=0$ dann $out = a$ sonst $out=b$ |

**Konsturution**
![[Pasted image 20260615134828.png]]

## Mux16
|               |                                                                                      |
| ------------- | ------------------------------------------------------------------------------------ |
| **Chipnanme** | Mux16                                                                                |
| **Eingänge**  | a\[16],b\[16], sel                                                                   |
| **Ausgägne**  | out\[16]                                                                             |
| **Funktion**  | Wenn $sel=0$ dann für $i=0\dots 15$ $out[i]=a[i]$ sonst für $i=0\dots 15$ $out=b[i]$ |

### Mux4Way16
|               |                                                                                                                                        |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | Mux4Way16                                                                                                                              |
| **Eingänge**  | a\[16] ,b\[16], c\[16], d\[16], sel\[2]                                                                                                |
| **Ausgägne**  | out\[16]                                                                                                                               |
| **Funktion**  | Wenn $sel=00$ dann $out=a$<br>sonst wenn $sel=01$ dann $out=b$<br>sonst wenn $sel=10$ dann $out=c$<br>sonst wenn $sel=11$ dann $out=d$ |
![[Pasted image 20260615135820.png]]

### Mux48Way16
|               |                                                                                                             |
| ------------- | ----------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | Mux4Way16                                                                                                   |
| **Eingänge**  | a\[16] ,b\[16], c\[16], d\[16], e\[16], f\[16], g\[16], h\[16], sel\[2]                                     |
| **Ausgägne**  | out\[16]                                                                                                    |
| **Funktion**  | Wenn $sel=000$ dann $out=a$<br>sonst wenn $sel=01$ dann $out=b$<br>...<br>sonst wenn $sel=111$ dann $out=h$ |
![[Pasted image 20260615140008.png]]
