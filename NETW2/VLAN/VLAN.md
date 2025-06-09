>[!Definition]
>VLANs sind logische Verbindungen mit gleichen Geräten. VLANs bieten:
>- Segementierung von Geräten auf demselben Switch
>- Biete bessere Organisation
>- Broadcast, Multicast und Unicast werden isoliert
>- Kleinere Broadcast-Domain

Ohne VLAN erhalten alle Geräte welche mit demselben Switch verbunden sind alle Broadcast, Unicast und Multicast Nachrichten.
Mit VLANs sind diese Nachrichten auf ein VLAN reduziert und ohne Layer 3 Funktionalität können verschiedene VLANs nicht mehr miteinander kommunizieren.

**Vorteile von VLANs**

| Vorteil                   | Beschreibung                                                                 |
| ------------------------- | ---------------------------------------------------------------------------- |
| Kleinere Broadcast-Domain | Das Teilen des LANs führt zu kleineren Broadcast-Domains                     |
| Improved Security         | Nur Geräte desselben VLANs können miteinander kommunizieren                  |
| IT-Effizienz              | VLANs können Geräte mit ähnlichen Anforderungen gruppieren                   |
| Weniger Kosten            | Ein Switch kann mehrere VLANs unterstüzen                                    |
| Bessere Perfromance       | Kleine Broadcastdomains reduzieren Traffic und erhöht Bandbreite             |
| Einfaches Mangagement     | Ähnliche Gruppen benötigen ähnliche Applikation und andere Netzwerressourcen |

>[!Info]
>Das Mapping von VLAN zu Port ist im Flash-Memory gespeichert.

## VLAN Typen
### VLAN 1
VLAN 1 ist:
- Standard VLAN
- Standard Native VLAN
- Standard Management VLAN
- Kann nicht gelöscht werden.
### Data VLAN
Ein Data VLAN ist für den von Benutzer generierten Traffic. Standardmässig sind alle Port dem VLAN1 assigend, daher ist es auch das standard Data VLAN.

### Native VLAN
Das Native-Vlan ist nur für Trunk-Links.
Alle Packet welche über einen [[Trunk-Link]] gesendet werden, werden mit einem VLAN-Tag versendent ausser die des Native VLAN.

### Managment VLAN
Das Management VLAN wird für [[Remote Management Access]] genutzt und sollte kein Endbenutzer-Traffic ragen.
=> VLANs sin das SVI für Layer 2 Switches.

### Voice VLAN
Ein separates VLAN wird für Vice-Traffice benötigt.
Voic-Traffice benötigt:
- Reservierte Bandbreite,
- Hohe [[Quality of Service]] Prioritt
- Möglichkeit Verstopfungen zu meiden
- Weniger als 150ms Verzögerung.
=> Defaultmässig ist VLAN 150 für VoIP priorisiert.


## VLAN Identifikation
Ein IEE 802.Q Header ist 4 Bytes lang.

Der VLAN Tag wird vom Switch angefügt (wenn über den [[Trunk-Link]] gesendet wird) und wieder Entfernt, bevor er ein Endgerät erreicht.

Wird der Tag eingefügt/entfernt muss die FCS neu berechnet werden.

**802.1Q Tag**

| Feld                        | Funktion                                 |
| --------------------------- | ---------------------------------------- |
| Type                        | 2-Byte field mit Hexadezimal `0x8100`    |
| User-Priorität              | 3-bit Wert                               |
| Canonical Fomrat Identifier | 1-bit Wert welches Token-Ring unterstüzt |
| VLAN-ID                     | 12-bit VLAN ID (bis zu 4096 VLANs)       |

## Konfiguration
**Erstellen**
```
S1(config)# vlan vlan-id
S1(config-vlan)# name vlan-name
```

**Einem Port zuweisen**
```
S1(config-if)# switchport mode access
S1(config-if)# switport access vlan vlan-id
```
**Von Port entferen**
```
S1(config-if)# no switchport access vlan
```