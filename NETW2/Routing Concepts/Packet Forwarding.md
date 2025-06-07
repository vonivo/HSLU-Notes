Standardablauf eines Routers, wenn er einIP-Pakett erhält:
1.Pakett kommt auf Ingress-Interface an
1. Routeruntersuchtt Dest.-IP und konsultiert [[Routing-Tabelle]]
2. Router findet [[Path Determination|Longest Match]]
3. Routerverpackt IP-Paket in Layer-2 Paket.
4. Senden zu Next-Hop oder Destination.

Es gibt 3 Szenarien:
- **Directly Connected:** Router findet Dest MAC über ARP oder Neighbor Discovery) und versendet direkt an Ziel.
- **Next-Hop:** Router bestimmt "Next Hop", bestimmt dessen MAC und sendet.
- **No Match** -> Paket wird verworfen.

**Mechanismen**:
- **Process Switching**: Sehr Alt. JedePaketet wird an Control-Pane weitergeleitet und Destination gesucht.
- **Fast Switching**: Alt. Aufbau von Cache. Control-Pane wird entlastet, da gleiche Dest.-IPs aus dem cache genommen werden.
- **Cisco Express Forwarding (CEF)**: Neu. Aufbau von Forwarding Information Base (FIB) und Adjazenz-Tabellen. Cleveres Cache Handling.
