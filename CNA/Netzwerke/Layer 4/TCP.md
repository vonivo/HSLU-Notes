Das Transmission Control Protocol (TCP) gewährleistet eine zuverlässige Datenübertragung, ist [[Verbindungslose und verbindungsorientierte Dienste#Verbindungsorientiert|verbindungsorientiert]], gewährleistet einen fehlerfreien Datenstrom von einem Rechner zu anderen und führt [[Flusskontrolle|Flusskontrollen]] zur Geschwindigkeitsanpassung durch.

TCP bietet keine Unterstüzung für Multicast und Broadcast.

TCP ist eine Duplex-Verbindung und übermittelt einen Bytestrom.

# Beispiel
a) Vier 512 Byte grosse Segmente als separate Pakete via IP versendet.
b) 2048 Byte Daten werden beim Empfänger in einem Stück der Anwendung zur Verfügung gestellt. (Abruf mittels READ CALL)
![[TCP.png]]

# Auf- und Abbau
## Verbindungsaufbau
Der Verbindungsaufbau einer TCP-Verbindung erfolgt mit dem 3-Wege-Handshake:
![[TCP_Connect.png]]

## Verbindungsabbau
Der TCP-Abbau verläuft über ein FIN-Bit. Damit wird die Verbindung wieder freigegeben.
![[TCP_Disconnect.png]]

# TCP-Header
Der TCP-Header ist wie folgt aufgebaut:
![[TCP_Header.png]]
# Bekannte Ports

| Port   | Use        | Protocol                 |
| ------ | ---------- | ------------------------ |
| 20/21  | FTP        | File Transfer            |
| 23     | Telnet     | Remote login             |
| 25/587 | SMTP       | Email                    |
| 69     | TFTP       | Trivial File Transfer    |
| 79     | Finger     | Lookup info about a user |
| 80/443 | HTTP/HTTPS | World Wide Web           |
| 110    | Pop3       | Remote e-mail access     |
| 119    | NNTP       | USENET news              |
| 53     | DNS        | Domain-Name-System       |
