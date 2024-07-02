Die Flusskontrolle bezieht sich auf den Start-Punkt-zu-Endpunkt-Verkehr zwischen Sender und Empfänger in einem [[Netzwerke|Netzwerk]].

Die Flusskontrolle stellt sicher, dass ein schneller Sender einen langsamen Empfänger nicht "überflutet".

Die Flusskontrolle arbeitet daher auf dem [[Data-Link-Layer]] und dem [[Transport-Layer]].

**Problem**
Ein Sender möchte schneller senden, als der Empfänger die Daten verarbeiten kann.

**Lösungsansätze**
- Feedback-basierte Flusskontrolle -> Empfänger sendet Informationen an den Sender zurück.
- Flusskontrolle basierend auf der Übertragungsrate -> integrierter Mechanismus im Protokoll ([[Sliding Widndow Protocoll]]).

# Realisierung von Flow-Control
## Hardware Flow Control
In der Hardware-Flusskontrolle werden bei die Leitungen RTS (Request to send), CTS (Clear to send), DTR (Data Terminal Ready) und DSR (Data Set Ready) verwendet.

## Software Flow Control
Die Flusskontrolle kann auch mittels Software realisiert werden:
- Im ASCII-Zeichensatz sind die ersten 32 Zeichen für Steuerungsaufgaben reserviert.
- Von diesen 32 Zeichen sind vier (DC1 bis DC4) Gerätesteuerzeichen.

Die Software-Flow-Control nuntzt nun die Zeichen:
- `DC1`-> XON für Transmission ON
- `DC3` -> XOFF für Transmission OFF