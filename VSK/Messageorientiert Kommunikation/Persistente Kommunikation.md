>[!Definition]
>Bei persistenter Kommunikation wird die Nachricht (i. d. R. Disk) gespeichert, bis der Empfänger bereit ist. (z.B. Email).

## Persistente [[Messageorientierte Kommunikation]]
Für persistente messageorientierte Kommunikation wird meistens eine **Message-Oriented-Middleware** (MOM) genutzt.

Diese MOM **speichert** die Nachrichten zwischen, was eine **zeitversetzte** Kommunikation ermöglicht.
![[MOM.png]]
- Sender und Empfänger müssen nicht aktiv sein während Übertragung.
- Untersützt lange Transfers.

**Beispiele**
- Apache ActiveMQ/ ArtmeisMQ
- RabbitMQ
- WebsphereMQ

### Message Queuing-Model
Kommunikation durch Einfügen von Messages in Warteschlange von **Empfänger**.
- Keine Garantie, **wann** eine Nachricht verarbeitet wird.
- Message von MOMs werden weitergeleitet bis zum Ziel.
	- MOMs direkt miteinander Verbunden
	- Queses können geteilt werden, meistens aber eine Queue pro Empfänger
![[MessageQueuing.png]]
>[!Warning]
>Durch MessageQueues wird die Kommunikation zeitlich Entkoppelt.

![[MessageQueueZeitlicheEntkopplung.png]]

| Operation         | Beschreibugn                                                                                                                                            |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `put()`           | Füge eine Message einer Bestimmten Queue hinzu.                                                                                                         |
| `get()`           | Warte bis eine Queue nicht mehr leer ist und retourniere die erste Message in der Queue. => **blockierend**                                             |
| `poll()`          | Überprüfe ob eine Queue mindestens eine Message enthält.<br>Ist dies der Fall ist, retourniere die erste Message in der Queue. => **nicht blockierend** |
| `notify(callbck)` | Registriere eine Callback-Funktion, welche aufgerufen wird,<br>sobald eine Message in dieser Queue eintrifft.                                           |
**Populäre MessageQueuing Protokolle**
- **AMQP**: Ubiquitous, secure, reliable and open internet protocol for handling business messaging.
- **MQTT**: light weight, client to server, publish / subscribe messaging protocol. Oft im IoT-Bereich verwendet.
- **STOMP**: text-orientated wire protocol.
- **XMPP**: eXtensible Messaging and Presence Protocol.