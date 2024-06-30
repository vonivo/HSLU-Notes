Medium Access Control (MAC) sind Verfahren, welche den Zugriff auf einen [[Broadcast Kanal]] regelt.

Dabei wird geregelt, wer senden darf, damit möglichst wenig Kollisionen auftreten.

=> Regelt das Zugriffsrecht auf den Übertragungskanal -> **Zugriffsverfahren**.



# Statische Kanalzuordnung
Bei der Statischen Kanalzuordnung wird der Kanal statisch einem Sender zugeordnet:

**FDM -> Frequency Dvision Multiplexing**
- Die Bandbreite wird in Frequenzbereiche aufgeteilt.
- Jeder Benutzer erhält ein eigenes Frequenzband (bsp. UKW)

**TDM -> Time Division Multiplexing**
- Wei bei FDM, jedoch Aufteilung des Kanals in Zeitschlitze (nummeriert, wiederholt)

**CDMA -> Code Division Multiple Access**
- Wie bei FDM und TDM, jedoch Aufteilung der Codierung (Sprache).

**SDMA -> Space Division Multiple Access**
- Aufteilung des Raums z.B. in Funkzellen beim Mobiltelefon

=> Beim Mobilfunk werden alle 4 Methoden gleichzeitig verwendet.


# Dynamische Kanalzuordnung
Bei der dynamischen Kananlzuordnung geht man von einem Stationen-Modell aus (unabhängige Station die senden können).
Dabei existier nur ein Kanal.

Wenn gelichzeitig zwei Frames übertragen werden, spricht man von einer Kollision.

**Protokolle:**
- [[ALOHA]]
- [[CSMA]]
- kollisionsfreie Protokolle

**Kolisionsfrei Protokolle**
- Tokenring -> Synchronisierung durch umlaufendes Token
- Bitmusterprotokolle, Bit-Arbitrierung
	- Jeder Teilnehmer hat eine Kennung (ID) oder Zahl die seiner Priorität entspricht.
	- Auch als CMSA/CR (Collision Resolution) bezeichnet
	- Teilnehmer senen z.B. gleichzeitig, beginnend mit dem höchst-wertigsten Bit ihrere Kennung.
	- Sobald eine Tielnehmer einen anderen Sender mit einer höheren Kennung erkennt zieht er sich zurück
	- => CAN-Bus
- 