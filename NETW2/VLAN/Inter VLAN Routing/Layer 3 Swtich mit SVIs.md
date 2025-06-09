Der Moderne Weg für [[Inter VLAN Routing]] ist mit Layer 3 Switches. Diese besitzen **Switched Virtual Interfaces**, welche das Routing vornehmen können.
![[Layer3-Switch.png]]
- Inter-VLAN SVIs werden gleich erstellt wie das SVI für das Management VLAN [[Remote Management Access]]

**Vorteile**
- Schneller als [[Router-on-a-Stick]], da alles hardware-switched und routed ist.
- Keine externen Links benötigt.
- Sind nicht uf eine Layer 2 Link limitiert, da [[EtherChannel]] verwendet werden kann.
- Tiefere Latenz, da alles auf dem gleichen Gerät gemacht wird.

## Configuration
1. [[NETW2/VLAN/VLAN|VLAN]] erstellen.
2. SVI VLAN erstellen -> IP-Adresse ist default-gateway für Hosts im selben VLAN (Hosts müssen dieses auch so Verwenden)
3. Access-Ports konfigurieren
4. IP-Routing einschalten `ip routing`

**Routing zu Router konfigurieren:**
1. Router Port konfigurieren mit `no switchport`, IP-Adresse und Sbunetzmaske assignen
2. `ip routing` Global aktivieren
