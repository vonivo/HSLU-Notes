![[Pasted image 20260615133438.png]]

|               |                                                                                     |
| ------------- | ----------------------------------------------------------------------------------- |
| **Chipnanme** | Nand                                                                                |
| **Eingänge**  | a,b                                                                                 |
| **Ausgägne**  | out                                                                                 |
| **Funktion**  | Wenn $a = b = 1$ dann $out =0$ sononst $out =1$                                     |
| **Kommentar** | Dieses Gatter wird als primitv angesehen und muss daher nicht implementiert werden. |



Wahrheitstabelle:

| x   | y   | x NAND y |
| --- | --- | -------- |
| 0   | 0   | 1        |
| 0   | 1   | 1        |
| 1   | 0   | 1        |
| 1   | 1   | 0        |
>[!Info]
>Jede der Operationen, [[AND]], [[OR]], [[NOT]] kann aus **NAND**(/NOR) und nur aus **NAND**(/NOR) konstruiert werden.

**Beispiel**
x OR y = (x NAND x) NAND (y NAND y)

>[!Info]
>Da jede [[Boolesche Funktion]] mit aus den Operatoren [[AND]], [[OR]], [[NOT]] gebaut werden kann, kann somit jede boolesche Funktion nur aus NAND gebaut werden.



