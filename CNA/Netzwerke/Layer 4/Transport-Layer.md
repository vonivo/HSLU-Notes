Der Transport-Layer ist der vierte Layer des [[OSI Referenzmodell]] und ist die erste End-zu-End-Verbindung im Stack.

Das heisst, dass eine Anwendung direkt mit der Anwendung eines anderen Computers kommuniziert. (Aus der Sicht der Transportschicht ist das gesammte Internet nur ein einziger Kanal):
![[TransportLayer.png]]

Die zwei grossen Protokollen im Transport-Layer sind:
- [[TCP]]
- [[UDP]]

Das [[IP|IP-Protokoll]] bietet nur einen unzuverlässigen Datagrammdienst.
Die Transportschicht benutzt das IP-Protokoll, baut daraus einen zuverlässigen Datendienst.

# Aufgaben
Die Transportschicht erledigt folgende Aufgaben:
- Verlorene, gestörte Pakete erkennen und durch **Wiederholung der Übertragung** korrigieren.
- Die Mängel der Vermittlungsschit werden verborgen.
- Einheitliche Dienste-Schnittstellen für übergeordnete Schicht, unabhängig von der verwendeten Vermittlungsschicht.

## Mögliche Probleme
Die Transportschicht fängt folgende mögliche Probleme ab:
- verlorene oder defekte/gestörte Pakete.
- Pakete kommen verspätet an.
- Verzögerungszeiten sind variabel, abhängig von der Netzlast.
- Pakete können doppelt ankommen.
- Datenstau, Anhäufungen von empfangenen Paketen.
- Neubooten von Rechnern und Wiederaufnahme einer laufenden Übertragung.
- etc.

## Lösungssätze
- Durchnummerieren aller Pakete mit Folgenummern.
- Anforderungen und Bestätigungen.
- Beschränkun der Lebensdauer von Paketen (Zeitstempel, Überwachung mit Timer).
- Verbindungsaufbau mti 3-Wege-Handshake
	1. Connection Request (Anforderungen mit Folgenummer x)
	2. Acknowledge (Bestätigung mit Bestätigung x und neuer Folgenummer y)
	3. Erstes Datenpaket mit Bestätigung y
	

# Service-Primitives

| Primitive  | Packet sent     | Meaning                                    |
| ---------- | --------------- | ------------------------------------------ |
| LISTEN     | (none)          | Block until some process tries to connect  |
| CONNECT    | CONNECTION REQ. | Actively attempt to establish a connection |
| SEND       | DATA            | Send information                           |
| RECEIVE    | (none)          | Block until a DATA packet arrives          |
| DISCONNECT | DISCONNECT REQ. | This side wants to release the connection. |
# Schichte-Modell
![[TransportLayer_2.png]]

