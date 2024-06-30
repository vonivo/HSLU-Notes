![[IEEE_802.png]]
# Ethernet
Ein Ethernet-Frame sieht wie folgt aus:
![[Ethernet.png]]
- Präambel (=Flag): `101010...` -> 5MHz Wellen zur Regenerierung des Sendetakt. (64 Bit)
- [[Adressräume#MAC-Adressen|MAC-Zieladresse]]: 48 Bit
	- `0xxx...xxx` -> unicast
	- `1xxx...xxx` -> Multicast
	- `111...111` -> Broadcast
- MAC-Quelladresse
- Daten: Transparent, d.h. alle Bitmuster erlaubt, 0 bis **1500 Bytes**.
- [[CRC]]