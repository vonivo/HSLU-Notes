![[Pasted image 20260618100358.png]]

|               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Chipnanme** | CPU                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Eingänge**  | `inM[16]`                -> Memory-Wert eingang<br>`instruction[16]` -> Auszuführende Anweisung<br>`reset`                    -> Signalisert ob PC resettet wird                                                                                                                                                                                                                                                                                                                                   |
| **Ausgägne**  | `outM[16]`              -> Ausgabe des M-Werts<br>`writeM`                  -> Ob in M geschrieben wird<br>`addressM[15]`       -> Speicher Adresse von M<br>`pc[15]`                  -> Adresse der nächsten Anweisung                                                                                                                                                                                                                                                                           |
| **Funktion**  | Führt die Anweisung gemäss der Spezifikation der Hack-Maschinensprache aus. `D` und `A` in der Sprache beziehen sich auf die internen Register, während sich `M` sich auf die durch `A` adressiert Speicherstelle in Memory bezieht.<br><br>Wird ins Memory geschrieben, werden die Daten in `outM` angelegt, zusätzlich wird die Zieladresse in `addressM` gesetzt und `writeM` auf `1` gesetzt.<br><br>Bei `reset=1` wird die Adresse `0` in den PC gesetzt und das Programm wird neu gestartet. |
![[Pasted image 20260618101016.png]]
**Konstruktion**
![[Pasted image 20260618101553.png]]


### Befehlsdekodierung
Die Form eines Worts sieht wie folgt aus:
`i xx a cccccc ddd jjj`

Das `i`-Bit zeigt den Befehlstyp. Wenn dieser `0` ist werden das gesammte Wort in das `A`-Register geladnen. (Wichtig: alle anderen Steuerbits dürfen nichts verändern -> [[AND]]-Gates).
Ansonste muss alles sauber verknüpft werden. `c` Teil dabei straight forward und, der `d`-Teil welcher steuert wo was gespeichert wird etwas kompliziert.

Der `j` Dabei wieder etwas eifacher.

