Das User Datagram Protocol (UDP) ist ein Datagramm-Dienst, welcher unzuverlässig, [[Verbindungslose und verbindungsorientierte Dienste#Verbindungslos|verbindungslos]] und für einmalige, schnelle Übertragungen verwendet wird.


UPD arbeitet nach dem **Best effort**-Prinzip. Sprich Datagramme können verloren gehen, werden in falscher Reihenfolge geliefert etc.
Einzig eine optionale Checksumme garantiert die Datenintegrität.

Jede UDP Datenübertragung legt die IP-Adresse und die Portnummer des Senders und Empfängers fest.

# UDP-Paket
Das UDP-Protokoll ist sehr einfach und besitzt im Wesentlichen:
- Header mit Quell- und Zielport, Paketlänge und Checksumme.
- Nutzlast (SDU)
![[UDP.png]]
Ein UDP Header besteht aus 8 Byte.

# Anwendungen
Typische UDP-Anwendungen sind:
- Kommunikation im Client-Server-Betrieb
	- Client sendet kurze Anforderung an Server
	- Server führt Anfrage aus und sendet kurze Antwort
- [[RPC]]
- [[RTP]]
- DNS
