Bei einem Broadcast können mehrere Sender auf einen Übertragungskanal zugreifen. Nachrichten werden dabei als [[Dataframes]] versendet und können von allen angeschlossenen Rechnern gleichzeitig empfangen werden.

Ein Adressfled im Frame gibt das Ziel an:
- Unicast -> Versand an einen einzelnen Empfänger
- Broadcast -> Versand an alle
- Multicast -> Versand an eine Gruppe
- Anycast -> Versand an einen (beliebigen) Rechner aus einer Gruppe

Ein Broadcast-Kanal wird auch bezeichnet als:
- Mehrfachzugriffskanal / Multiacces Channel
- Random Access Channel

Der Zugriff auf den Kanal wird über [[MAC]] gesteuert.