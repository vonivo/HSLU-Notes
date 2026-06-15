![[Pasted image 20260615151334.png]]

|               |                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | ALU                                                                                                                                                                                                                                                                                                                                                                              |
| **Eingänge**  | x\[16], y\[16] -> Zwei 16-Bit Eingänge<br>zx                  -> Nullstellung des x-Eingangs<br>nx                  -> Negieren des x-Eingangs<br>zy                  -> Nullstellung des y-Eingangs<br>ny                  -> Negieren des y-Eingangs<br>f                     -> Funktionscode: 1 für addieren, 0 für AND<br>no                  -> Negieren der Ausgabe $out$ |
| **Ausgägne**  | out\[16]         -> 16-Bit Ausgang<br>zr,                 -> 1 wenn $out =0$<br>ng                 -> 1 wenn $out <0$                                                                                                                                                                                                                                                            |
| **Funktion**  | Wenn $zx=1$ dann $x=0$<br>Wenn $nx=1$ dann $x=!x$<br>Wenn $xz=1$ dann $y$<br>Wenn $xy=1$ dann $y=!a$<br>Wenn $f=1$ dann $out=x+y$ sonst $out=x\&y$<br>Wenn $no=1$ dann $out = !out$<br>Wenn $out=0$ dann $zr=1$  sonst $zr=0$<br>Wenn $out <0$ dann $ng=1$ sonst $ng =0$                                                                                                         |

**Konsturution**
![[Pasted image 20260615152103.png]]
## Funktionen
![[Pasted image 20260615152442.png]]
