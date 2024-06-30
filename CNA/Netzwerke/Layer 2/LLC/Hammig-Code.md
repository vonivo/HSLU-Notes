Hamming-Codes ist ein Error-Correction-Code der es erlaubt einen Code so zu Kodieren, dass Fehler erkannt und teilweise gerade verbessert werden können.

Der Hamming-Code basiert auf dem **Hamming-Abstand** $h$. Dieser Abstand gibt die kleinste Anzahl an Bits, in dene isch 2 **beliebige** Codewörter eines Codes unterscheiden.

**Beispiel**:
`10110011`
`11010010` 
=> Hamming-Abstand von 3.

Ein Hamming-Code ist nun eine Kodierung, bei der alle Codeworte einen definieren Abstand haben.

## Fehlererkennung und Korrektur
Um $e$ gleichzeitig auftretende Einzelbitfehler erkennen zu können, braucht man eine Kodierung mit einem Hamming-Abstand von:
$$
h = e+1
$$
Um $e$ Bitfehler korrigieren zu können,  braucht man einen Abstand von:
$$
h=2e+1
$$
