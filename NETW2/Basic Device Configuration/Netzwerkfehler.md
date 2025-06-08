Es gibt verschieden Netzwerkfehler mit dem Befehl `show interfaces` können einige angezeigt:

| Error Typ       | Beschreibung                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------ |
| Input Error     | Summe aller Fehler (inkludiert Runts, Giants, no buffer, CRC, frame, overrun und ignored counts) |
| Runts           | Pakete die zu klein sind für das Medium (z.B. Ethernet Paket kleiner als 64 Bytes)               |
| Giants          | Pakete die zu groß sind für das Medium (z.B. Ethernet Paket größer als 1518 Bytes)               |
| CRC             | Kalkulierte Checksumme nicht gleich wie erhaltene Checksumme                                     |
| Output Errors   | Summe aller Fehler welche das Senden verhindern (Collisions, Late Collisions)                    |
| Collisions      | Anzahl Kollisionen                                                                               |
| Late Collisions | Anzahl Kollisionen nachdem bereits 512 Bits übertragen wurden                                    |
