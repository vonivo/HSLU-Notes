Ein Router nutzt sein [[Routing-Tabelle]], um das Egress-Interface zu bestimmen. 

Dabei nutzt der das **Longest Match** Verfahren.
- Beim Longest Match Verfahren werden die Ziel-IP und die Netwerzkadresse der [[Routing-Tabelle]] verglichen
- Dass heisst, der längste Match von links nach rechts ist der nächste Hop.
- Ein Match  zählt nur, wenn mindestens die Anzahl Bit der Subnetzmaske gematcht werden.

**Beispiel**

| Destination IP | Binary                              |
| -------------- | ----------------------------------- |
| 172.16.0.10    | 10101100.00010000.00000000.00001010 |

| Entry | Prefix/Legth  | Binary                                  |
| ----- | ------------- | --------------------------------------- |
| 1     | 172.16.0.0/12 | **10101100.0001**0000.00000000.00001010 |
| 2     | 172.16.0.0/18 | **10101100.00010000.00**000000.00001010 |
| 3     | 172.16.0.0/26 | **10101100.00010000.00000000.00**001010 |
Eintrag drei hat hier den Longest match und würde gewählt werden.

Bei einem Router gibt folgende Netzwerke:
- **Directly Connected**: Direkt verbunden. (IP-Adresse auf einem lokalen Interface)
- **Remote**: Nicht direkt mit dem Router verbunden:
	- **Static Route**: Manuell konfiguriert
	- **Dynamic Route**: Dynamisch erlernt.
