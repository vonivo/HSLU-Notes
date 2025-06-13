CAPWap ist ein IEEE Standard welches einem [[Wireless LAN Controller]] erlaubt mehrere [[AP]]s und WLANs zu managen.

CAPWAP basiert auf LWAPP aber fügt zusätzliche sicherheit mit Datagram Transport Layer Security (DLTS) hinzu.

Es verpackt und forwaded WLAN Client Traffic zwischen AP und WLC über Tunnels mittels UDP auf Port 5246 und 5247.

Funktioniert mit IPv4 mit Protokol 17 und IPv6 mit Protokoll 136


## Split MAC Architekur
Die Split MAC Architektur von CAPWAP übernimmt alles Funktionen, welche ansonsten von AP gemacht werden und verteilt diese auf:
- AP MAC Funktionen
- WLC MAC Funktionen


| AP MAC Funktionen                        | WLC MAC Funktionen                                             |
| ---------------------------------------- | -------------------------------------------------------------- |
| Beacons und Beacon-Response              | Authentication                                                 |
| Paket quitierung und retransmission      | Association and re-<br>association of roaming<br>client        |
| Frame queuing und Priorisierung          | Frame translation zu anderen Protokollen                       |
| MAC layer Data encryption und decryption | Abschluss von 802.11 Traffic auf eine Kabelgebundens Interface |

## DTLS 
Datagram Transport Layer Security ist Encryption zwischen AP und WLC, zwei Tunnels, ein mal für Daten (not enabled by default, braucht Lizenz) und Control (encrypted by default)

## Flex Connect APs
FlexConnect erlaubt die Konfiguration von APs über ienen WAN-Link.

- **Connect Mode** WLC ist erreichbar. FlexConnect AP hat CAPWAP konnektivität mit dem WLC über einen CAPWAP Tunnel. WLC übernimmt CAPWAP funktionalität.
- **Standalone Mode**: WLC ist nicht erreichbar. FlexConnect AP nimmt einige CAPWAP Funktionaliät an (lokale)