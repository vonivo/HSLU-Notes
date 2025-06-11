---
aliases:
  - FHRP
---
Endgeräte besitzten meistens **nur ein Default-Gateway**. Wenn dieser offline geht, kann das Nezt nicht nach aussen kommunizieren.

>[!Definition]
>FHRP sind Mchanismen welche einen alternativen Default-Gateway für "switched Networks" zur Verfügung stellen.


## Router Redundanz
Ein Weg um diese Redundanz zu erstellen ist ein **Virtueller-Router**.
- Mehrere Router sind so konfiguriert, dass sie die Illusion von **nur einem Router** erstellen.
- Die verschiednen Router teilen sich:
	- [[IP-Adresse]]
	- [[MAC]]
- Nur der "**virtuelle Router**" ist als Default-Gateway konfiguriert.
- Clients senden an MAC (via [[ARP-Protokoll]]) -> wird nur vom "aktiven" Router des Clusters verarbeitet.
- Ähnlich wie [[Failover Cluster]]. Die physischen Router sind für die Endgeräte "unsichtbar"

**Ablauf**
1. Standby-Router empfängt keine `Hello-Msg` mehr.
2. Standby-Router nimmt Rolle des **forwarding Router** an.
3. Endgeräte spüren keine Downtime (da Virtuelle Adresse)

## Protokolle:
**HSRP**: Hot Standby Router Protocol
  - Cisco Properitär
  - Transparenter failover
  - Wird verwendet, um aktiv- und Standby Device zu wählen
**IPv6**: Gleich wie HSRP, einfach für IPv6
  - Virtuelle MAC von der HSRP Gruppennummer
  - virtuele IPv6 Link-Local Adresse
  - Router Advertisements werden auf die Link-Local Adresse gechickt, um zu signalisieren, dass der Router noch aktiv ist
  **VRRPv2**: Virtual Router Redundancy Protocol (Version 2)
  - Offenes Protokoll
  - Verantwortungsverteilung für virtuelle Router in IPv4 LAN
  - Ein "Master", mehrere Backups, master wird geählt von allen
**VRRPv3**: Ähnlich zu VRRPv2, einfach mit IPv6 Support, zudem bessere Skalierbarkeit
**GLBP**: Gateway Load Balancing Protocol
  - Cisco Properitär FHRP
  - Wie HSRP und VRRP aber mit zusätzlicher Möglichkeit für LoadBalancing / Load Sharding über mehrere Router
**GLBPv6**: GLBP mit IPv6 Support
**IRDP**: ICMP Router Discovery Protocol
  - RFC 1256, legacy
  - Wurde von Hosts verwendet, um router zu finden, welche non-local IP netzwerke ihnen zugänglich machen

## HSRP
**Active-Election**
Standardmässig ist immer der Router mit der numerisch höchsten IP der **aktive**.

Über die HSRP-Priorität kann das jedoch explizit gestuert werden:
- Standard HSRP-Priorität ist `100`
- Die Höchste HSRP-Priorität ist der **Active** -> Tiebreaker: IP
```
R1(config-if): standby priority <prio> # 0- 255
```

**Preemption**
Wenn ein Router einaml **Aktiv** ist, bleibt er der Aktive, auch wenn ein neuer Router mit niedriger Priorität online kommt.

Mit dem Befehl:
```
R1(config-if): standby preempt
```
Kann dieses Verhalten geändert werden und Router mit einer höheren Priorität starten eine Election-Prozess.

### Stati
- **Initial**: Durch config-change oder wenn das Interface zum ersten mal verfügbar wird
- **Learn**: router kennt die V-IP noch nicht und hat auch noch keine `hello` message vom aktiven router gesehen, er wartet vom Aktiven router zu hören
- **Listen**: Router kennt die virtuelle ip, hat aber noch nicht vom aktiven gehört und ist deshalb weder aktiv noch standby und wartet auf ein `hello`
- **Speak**: Router sendet periodische `hello`-Messages und partizipiert aktiv an der leader election
- **Standby**: Router ist kandidat, aktiv zu werden und sendet periodische `hello` requests
- **Active**: Router welcher die Election gewonnen hat

- Active und Standby Router senden alle 3 Sekunden ein `hello`-Packages auf die HSRP-Multicast-Adresse.
- Standby wird aktiv, wenn er innert 10 Sekunden keine `hello` vom Aktiven Router bekommt
- Kann beides konfiguriert werden
- hello-timer sollte nicht unter 1 Sec., hold timer nicht unter 4 Sec. sein $->$ CPU-Last gering halten