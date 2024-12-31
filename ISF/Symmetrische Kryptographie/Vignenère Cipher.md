- Ein Wort wird gewählt, jeder Buchstabe des zu verschlüsselnden Text wird mit dem Entsprechenden Stellen Wert aus dem Schlüsselwort verschoben
- Lange Schlüssel erhöht die Sicherheit nicht
- Problem: (Intervall-)Frequenzanalyse

Ablauf:
1. Wähle ein Schlüsselwort, z.B. CAESAR. Dies wird zu CAESR
2. Die Länge des Schlüssels ist hier $n=5$.
3. Der 1. Buchstabe des Klartextes wird mit einem Alphabet verschlüsselt, welches mit C beginnt.
4. Der 2. Buchstabe des Klartextes wird mit einem Alphabet verschlüsselt, welches mit A beginnt.
5. Der 3. Buchstabe des Klartextes wird mit einem Alphabet verschlüsselt, welches mit E beginnt.
6. So geht das weiter bis man beim 5. Buchstabe angekommen ist. Dieser wird dann mit einem Alphabet verschlüsselt welches mit R beginnt.
7. Anschließend wird diese Prozedur wiederholt, bis mal alles verschlüsselt hat.

![[Pasted image 20241231085323.png]]![[Pasted image 20241231085330.png]]
