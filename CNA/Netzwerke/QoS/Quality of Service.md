Die Quality of Service (QoS) misst die Qualität eines Neztwerks und ist in folgende Attribute unterteilt:
- Bandwith
- Delay
- Jitter
- Loss

# Anfroderungen an QoS-Parameter

| Application       | Bandwith | Delay  | Jitter | Loss   |
| ----------------- | -------- | ------ | ------ | ------ |
| Email             | Low      | Low    | Low    | Meidum |
| Filesharing       | High     | Low    | Low    | Medium |
| Web Access        | Medium   | Medium | Low    | Medium |
| Remote Login      | Low      | Medium | Medium | Medium |
| Audio on demand   | Low      | Low    | High   | Low    |
| Video on demand   | HIgh     | Low    | High   | Low    |
| Telephony         | Low      | High   | High   | Low    |
| Videoconferencing | High     | High   | High   | Low    |
## Applikationsbezogen

| Network Service             | Application       |
| --------------------------- | ----------------- |
| Constant bit rate           | Telephony         |
| Real-time variable bit rate | Videoconferencing |
| Non-real-time bit rate      | Video on demand   |
| Available bit rate          | File transfer     |

# Massnahmen
Um die Dienstgüte zu Gewährleisten können folgende Methoden benutzt werden:
- Bereitstellen von Ressroucen im Überfluss.
- [[Buffering|Zwischenpuffern]].
- [[Traffic-Shaping]].
	- [[Leaky-Bucket]]
	- [[Token-Bucket]]
- Revervieren von Ressourcen.
	- Bandbreite
	- Pufferspeicher
	- CPU-Zyklen
- Zeitliche Planung von Paketen (Paket-Scheduling).
	Gefahr: Aggressiever Sender belget Grossteil der Kanalkapaziät.
	-> Reduziert Dienstügte für andere Sender
	=> separate Warteschlange für jeden Sender und Fairer Algorithmus
	=> Sortierung der Pakete nach Beendigungszeit
	=> Sender der Pakete nach Beendigungszeit

![[PacketScheduling.png]]
- Proportionales Routing (bei zu Schneller Sendung -> Umweg)
- [[Zugangssteuerung]]


# IPv4 & IPv6
Bie IPv4 wird die QoS über das Feld ToS (Type-Of-Service) geregelt.

Beim IPv6 über das Flag DSCP