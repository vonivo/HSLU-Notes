![[Pasted image 20260615165648.png]]

|               |                                                                                                                                                                                                             |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | RAMn                                                                                                                                                                                                        |
| **Eingänge**  | in\[16], address\[k], load     -> $k=\log_{2}(n)$                                                                                                                                                           |
| **Ausgägne**  | out\[16]                                                                                                                                                                                                    |
| **Funktion**  | Sei $address(t-1)=j$.<br>Wenn $load(t-1)=1$ dann $out(t)=in(t-1)$ für $\text{address}(t)=j$<br>und $out(t)=out(t-1)$ für $\text{address}(t)\neq j$ <br>sonst $out(t)=out(t-1)$ für alle $\text{address}(t)$ |
**Konstruktion**
![[Pasted image 20260615170905.png]]

Der RAM Baustein hat drei Eingänge:
- Dateneingang -> Daten welche gespeichert werden sollen (bei read leer)
- Adresseingang -> Addresse von welcher gelesen/geschrieben werden soll
- Ladebit -> Zeigt an, ob geschrieben werden soll.($load=0$ -> Lesen, $load=1$ -> Schreiben)

RAM steht für Random-Access-Memory und ist ein [[Speicherelemente|Speicherelement]], welches direkten Zugriff erlaubt.

Ran ist eine Anordnung von $n$ $w$-Bit-[[Register|Registern]]. Die Anzhal der $n$ Register und die Breite $w$ der einzelnen Register werden als **Grösse** bzw. **Breite** des Speichers bezeichnet.

Der RAM kann dabei hierarchisch aufgebaut werden:
![[Pasted image 20260615170125.png]]


## Operationen
**Schreiben**
Die Schreiboperation ist abhängig vom Takt.

**Lesen**
Die Leseoperation ist taktunabhängig und so rein kombinatorisch.


### Addressierungsschema
Ein RAM64 kann auch einer Anordnung von acht RAM8-Chips aufgebaut werden. Um ein bestimmtes Register aus dem RAM64-Chip auszuwählen, verwenden wir eine 6-Bit-Addresse (z.B. $xxxyyy$). Mit den $xxx$-Bits wird der RAM8-Chip ausgewählt und mit den $yyy$-Bits dann ein Register innerhalb des ausgewählten RAM8-Chips.

