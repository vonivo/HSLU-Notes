>[!Definition]
>ZeroMQ ist eine Library für messageorientierte Kommunikation. Message werden in der Regel [[Asynchrone Kommunikation|asynchron]] gesendt.

ZeroMQ:
- [[Transiente Kommunikation]]: Messages werden nur im flüchtigen Speicher vorgehalten.
- Bekanntes Socket-Prinzip auf höherem Abstraktionslevel.
	- Spezifische Sockets für bestimmte [[Kommunikationsmuster]]
- Beliebiger Messageinhalt. (Binär oder Text)
- Framing basierend auf Länge.


**Wichtigste Sockets**

| Pattern               | Socket   | Einsatzgebiet                                        |
| --------------------- | -------- | ---------------------------------------------------- |
| [[Request-Reply]]     | -REQ<br> | Sendet Anfragen (an RES-Socket). Half Duplex<br>     |
|                       | -RES     | -Beantwortete Anfragen (von REQ-Socket). Half-Duplex |
| [[Publish-Subscribe]] | PUB      | Publiziert Message unter bestimmtem Topic.           |
|                       | SUB      | Empfängt Messages für abonnierte Topics.             |
| [[Pipeline]]          | PUSH     | Sendet Message an Verarbeiter (PULL-Socket).         |
|                       | PULL     | Empfängt Message zur Verarbeitung (von PUSH-Socket). |
