Die Version 6 des [[IP|IP-Protokoll]] ist seit 1998 standardisiert, aber sehr komplex und deshalb erfolgt die Anbindung von Endkunden erst seit 2011/2012.

Es existiert eine neues Adressformat: Nun werden 128-Bit-Adressen à 8x16-Blöcke vergeben (in Hex):
`2001:0db8:85a3:08d3:1319:8a2e:0370:7344`

Was nun die möglichen Adressen extrem vergrössert -> von $2^{32}$ auf $2^{128}$.

# Schreibweise
1. Normalerweise 8\*16 bit in Hex:
`2001:0db8:0000:0000:0000:8a2e:0070:7344`
2. Führende Nullen im Block ev. wegglassen:
`2001:db8:0:0:0:8a2e:70:7344`
3. 0er-Blöcke weglassen durch `::` ersetzen
`2001:db8::8a2e:70:7344` -> aber nur 1 mal pro Adresse
4. Letzen zwei Blöcke als Dezimalnotation erlaubt
`::ffff:7f001:1` -> `::ffff:127.0.0.1` -> (IPv4 einbetten)
5. URL-Notation möglich (in `[]` angeben)
`http://[2001_0db8:85a3:08d3::0370:7344]:8080/

# Sepzielle Adressen
- `::/128` (128 0-Bit) => nicht spezifiziert, beliebig
- `::1` -> loopback, localhost
- `fe80::/10`Link-Local-Unicast-Adr (IPv4 APIPA)
- `fec0::/10`Site-Local-Unicast-Adr (IPv4 priv. Adr)
- `fc00::/7` Unique-Local-Unicast (priv Adresen)
- Global-Unicast
	- `0:0:0:0:0:ffff::/96` IPv4 mappped (letze 32-Bit=IPv4)
	- `2000::/3` (200... bis 3fff): von IANA bisher eindeutig Vergeben.

# Features
- Unterstüzung für Authentifizierung, Security, Verschlüsselung, z.B. neuer Dienst [[IPSec]]
- Vereinfachung und Verbesserung der Protokollheader -> Einfacher für [[CNA/Netzwerke/Layer 3/Router|Router]]
- Unterstüzung für Mobile IP und vereinfachte Umnummerierung (beim Umzug von Rechner)
- Autokonfiguration von IPv6-Adressen ([[CNA/Netzwerke/Layer 3/Internet-Protokoll/DHCP]] wird überflüssig)
- [[Quality of Service]]

# IPv6 Header
![[IPv6Header.png]]

| Feld                | Länge   | Inahlt                                                                                               |
| ------------------- | ------- | ---------------------------------------------------------------------------------------------------- |
| Version             | 4 Bit   | IP-Versionsnummer 6                                                                                  |
| Traffic-Class       | 8 Bit   | [[Quality of Service]]                                                                               |
| Flow Label          | 20 Bit  | Ebenfalls für [[Quality of Service]] oder Echtzeitanwendungen                                        |
| Payloadlength       | 16 Bit  | Länge des IPv6 Paketinhalt (ohne Kopfdatenbereich, aber inklusiv der Erweiterungs-Kopfdaten) in Byte |
| Next Header         | 8 Bit   | Typ des nächsten Kopfdatenbereiches                                                                  |
| Hop Limit           | 8 Bit   | Entsprich TTL                                                                                        |
| Source Address      | 128 Bit | Sender                                                                                               |
| Destination Address | 128 Bit | Empfänger                                                                                            |
