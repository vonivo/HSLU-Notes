EtherChannel ist eine Technologie die es erlaubt mehrere physische Links zwischen zwei Switches zu einem logischen Link zusammenzufassen.
![[EtherChannel.png]]
Ein logischer Link, wird dabei Port-Channel genannt.
Die physischen Interfaces werden zu einem Port-Channel zusammengefasst.

**Vorteile**
- Viele Konfigurations-Einstellungen können direkt auf dem Port-Channel gemacht werden.
- Da EtherChannel auf den existieren Switch-Ports basiert, müssen diese nicht geupgraded werden, um den Speed zu erhöhen.
- Mit EtherChannel findet ein Loadbalancing statt.
- Ein EtherChannel wird als ein logischer Link von [[Spanning Tree Protokoll]] behandelt.
- Ein Ausfall eines physischen Links beeinflusst den EtherChannel nicht.

**Einschränkungen**
- Interface-Types können nicht gemischt werden.
- Ein EtherChannel kann maximal 8 Links unterstützen.
- Es können bis zu 6 EtherChannels gebildet werden.
- Die gegenüberliegenden Ports eines Links müssen dieselbe Konfiguration habe.

## Autonegation
Wie beim [[Dynamic Trunking Protocol]] gibt es auch für EtherChannel ein automatisches Verhandlungsprotokoll. Dabei Kann zwischen Port-Aggregation-Protocol (PAgP, Cisco propertiär) und Link Aggregation Control Protocol (LACP) gewählt werden

### PAgP
In PAgP können folgende Modi konfiguriert werden:
- **On** - Forciert die einen EtherChannel ohne PAgP.
- **PAgP desirable**: Platziert das Interface in einem aktiven Verhandlungsstatus.
- **PAgP auto**: Platziert das Interface in einem passiven Verhandlungsstatus.

| S1          | S2                 | Kanalbildung? |
| ----------- | ------------------ | ------------- |
| `on`        | `on`               | Ja            |
| `on`        | `desirable`/`auto` | Nein          |
| `desirable` | `desirable`        | ja            |
| `desirable` | `auto`             | ja            |
| `auto`      | `desirable`        | ja            |
| `auto`      | `auto`             | nein          |


### LACP
In LACP können folgende Modi konfiguriert werden:
- **On**: Forciert die einen EtherChannel ohne LACP.
- **LACP active:** Platziert das Interface in einem aktiven Verhandlungsstatus.
- **LACP passive:** Platziert das Interface in einem passiven Verhandlungsstatus.

| S1        | S2                 | Kanalbildung? |
| --------- | ------------------ | ------------- |
| `on`      | `on`               | Ja            |
| `on`      | `active`/`passive` | Nein          |
| `active`  | `active`           | ja            |
| `active`  | `passive`          | ja            |
| `passive` | `active`           | ja            |
| `passive` | `passive`          | nein          |

## Konfiguration
**Vorraussetzugen:**
- Alle Ports müssen EtherChannel unterstützen.
- Alle Port müssen dieselben [[Duplex und Speed]] Einstellungen haben.
- Alle Ports müssen im selben VLAN sein.
- Bei einem Trunk-Etherchannel ([[Trunk-Link]]) müssen dieselben allowed [[NETW2/VLAN/VLAN|VLAN]] sein.

1. Interfaces auswählen und mittles `range` alle gleichzeigitg bearbeiten.
2. Channel Gruppe erstellen
3. Um Layer2 Settings auf dem Port-Channel zu setzen `interface port-channel <id>` nutzen. (z.B. für VLAN allow list)

```
 interface range fa0/1 - 2
S1(config-if-range)# channel-group <ID> mode <mode PAgP/LACP>
S1(config-if-range)# exit
S1(config)# interface port-channel <ID>
S1(config-if)# Layer 2 settings
```