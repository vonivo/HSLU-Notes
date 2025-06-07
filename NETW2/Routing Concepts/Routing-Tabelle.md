Die Routing Tabelle beinhaltete mindestens **Netzwerkadresse** (Prefix), **Egress-Interface** und eine **Subnetzmaske**. Die Prefix-Lenght bestimmt, wie viele Bits von Links matchen müssen, damit das Paket überhaupt dorthin weitergeleitet werden kann.


**Beispiel**

| Code | Prefix/Mask | Trust/Metrik | via IP   | Zeitstempel | Interface |
| ---- | ----------- | ------------ | -------- | ----------- | --------- |
| O    | 10.0.4.0/24 | \[110\|60]   | 10.0.3.2 | 00:24:22    | S0/1/1    |

**Attribute**:
- **Code:**
	- **L**: Adresse welche dem Router-Interface assigned ist.
	- **C**: Directly Connected.
	- **S**: Statisch erstellte Route
	- **O**: Dynamisch gelernte Route (OSPF)
- **Prefix**/**Mask**: Ziel-Netz
- **Administrative Distanz**: Vertrauenswürdigkeit. Tiefer = besser ->
	z.B.: C besser als O
- **Metrik**: Kosten/ Entfernung Tiefer = besser
- **TimeStamp**: Timestamp seit erlernen der Route.
- **Interface**: Ausgangsport

**Directly-Connected** wenn das Interfact aktiv ist und eine IP konfiguriert hat. Zu jedem C existiert ein L. Packet welche für ein lokales Interface bestimmt haben einen Prefix von 32 / 64 Bit. (Erkenunnung, damit sie nicht weiter geroutet werden.)

**Static-Routes** für
- Default route zu provider
- Routes ausserhalb der Routing-Domain
- Expliziter Pfad notwendig
- Routing zwischen Staub-Netzwerke

**Static vs Dynamic**

| Feature               | Dynamic                                | Static                |
| --------------------- | -------------------------------------- | --------------------- |
| Configuration Komplex | Unabhänign von Netz-Grösse             | Wächst mit Netzgrösse |
| Topology Changes      | automatisch                            | manuell               |
| Scalability           | Für komplexe Netzwerke                 | einfach topologien    |
| Security              | Muss konfiguriert werden               | inherent              |
| Resource Usage        | Braucht CPU, Bandbreite, speicher link | keine                 |
| Path predicability    | dynamisch                              | explizit.             |


**Default-Route**: Matcht alles, kommt am Schluss (0.0.0.0/0, ::/0)

**Administrative Distanz**

| Source              | Distanz |
| ------------------- | ------- |
| Directly Connectec  | 0       |
| Static Route        | 1       |
| EIGRP summary route | 5       |
| External BGP        | 20      |
| Internal EIGRP      | 90      |
| OSPF                | 110     |
| IS-IS               | 115     |
| RIP                 | 120     |
| External EIGRP      | 170     |
| Internal BGP        | 200     |


## Routing-Tabelle Prinzipien
- Jeder Router trifft Entscheidungen allein.
- Verschiedene Router = verschieden Routing-Tables.
- Routinginformationen zu einem Ziel heisst nicht, dass Rückweg auch bekannt ist.

## Routing Protokolle
![[routing_protokoll.png]]**Metrik** (für Berechnung der besten Route)
- RIP -> Hop-Count
- OSPF -> cost: Kumulative Bandbreite
- EIGRP: langsamtes Bandbreite und delay

**Loadbalancing**: Aufteilen von Paketen auf verschieden Routes. (automatisch bei dynamic routing protocols)