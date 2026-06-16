![[Pasted image 20260615170929.png]]

|               |                                                                                                                                                                              |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | PC                                                                                                                                                                           |
| **Eingänge**  | in\[16], inc, load, reset                                                                                                                                                    |
| **Ausgägne**  | out\[16]                                                                                                                                                                     |
| **Funktion**  | Wenn $\text{reset}(t-1) =1$ dann $out(t)=0$<br>sonst wenn $load(t-1)=1$ dann $out(t)=in(t-1)$<br>sonst wenn $inc(t-1)=1$ dann $out(t)=out(t-1)+1$<br>sonst $out(t)=out(t-1)$ |
**Konstruktion**
![[Pasted image 20260615171525.png]]

![[Pasted image 20260615171140.png]]


Der Zähler ist ein sequentieller Chip, dessen Zustand eine ganze Zahl ist, die in jeder Zeiteinheit inktrementiert wird, als die Funktion $out(t)=out(t-1)+c$ ausführt, wobie $c$ normalerweise $1$ ist.

Bei der Hack-Plattform wird die Ausgabe des PCs als die Addresse des Befehls interpretiert, der als nächstes im aktuellen Programm ausgeführt werden soll.