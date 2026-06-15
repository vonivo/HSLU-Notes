![[Pasted image 20260615134412.png]]

|               |                                                          |
| ------------- | -------------------------------------------------------- |
| **Chipnanme** | Mux                                                      |
| **Eingänge**  | in, sel                                                  |
| **Ausgägne**  | a, b                                                     |
| **Funktion**  | Wenn $sel=0$ dann $\{a=in, b=0\}$ sonst  $\{a=0, b=in\}$ |

**Konsturution**
![[Pasted image 20260615135000.png]]
### Mux4Way

|               |                                                                                                                                                                                                       |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | Mux4Way16                                                                                                                                                                                             |
| **Eingänge**  | in, sel\[2]                                                                                                                                                                                           |
| **Ausgägne**  | a, b, c, d                                                                                                                                                                                            |
| **Funktion**  | Wenn $sel=00$ dann $out=\{a=in, b=c=d=0\}$<br>sonst wenn $sel=01$ dann $out=\{b=in, a=c=d=0\}$<br>sonst wenn $sel=10$ dann $out=\{c=in, a=b=d=0\}$<br>sonst wenn $sel=11$ dann  $out=\{d=in, a=b=c\}$ |
![[Pasted image 20260615140247.png]]
### Mux8Way

|               |                                                                                                                         |
| ------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | Mux4Way16                                                                                                               |
| **Eingänge**  | in, sel\[3]                                                                                                             |
| **Ausgägne**  | a, b, c, d, e, f, g, h                                                                                                  |
| **Funktion**  | Wenn $sel=000$ dann $out=\{a=in, b=c=d=e=f=g=h=0\}$<br>sonst wenn $sel=001$ dann $out=\{b=in, a=c=d=e=f=g=h0\}$<br>.... |
![[Pasted image 20260615140355.png]]
