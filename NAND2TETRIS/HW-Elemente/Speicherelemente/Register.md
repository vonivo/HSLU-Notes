>[!Definition]
>Ein Register ist ein Speicherelement, das einen Wert über die Zeit hinweg speichern kann, indem es das klassische Speicherverhalten $out(t)=out(t-1)$ implementiert. Ein [[DFF]] hingenen kann nur seine vorherige Eingabe ausgeben.

![[Pasted image 20260615163634.png]]

|               |                                                            |
| ------------- | ---------------------------------------------------------- |
| **Chipnanme** | Register                                                   |
| **Eingänge**  | in\[16], load                                              |
| **Ausgägne**  | out\[16]                                                   |
| **Funktion**  | Wenn $load(t-1)=1$ dann $out=in(t-1)$ sonst $out=out(t-1)$ |


**Konstruktion**
![[Pasted image 20260615164546.png]]

>[!Info]
>Inhalte solcher Register werden üblicherweise als Wörter bezeichnet.
>Anzahl der Bits die es aufnehmen kann.


**Schreiben**
Um ein Wort in das Register zu schreiben, wird $D$ in den $in$-Eingang des Registers gelegt. Zusätzlich wird noch das $Write$-Bit aktiviert. Im nächsten Takt-Zyklus liegt dann $D$ auf dem $out$-Ausgang an.