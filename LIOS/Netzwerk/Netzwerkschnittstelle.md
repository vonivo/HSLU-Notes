Jede Netzwerkschnittstelle eines [[Linux]] hat einen Namen, der zur Konfiguration und Identifikation verwendet wird.

Jede Netzwerkschnittstelle ist einer Netzwerkkarte zugeordnet: LAN, WLAN, WWAN, etc.

# Namensgebung
## Alt
In älteren Versionen von Red Hat Enterprise wurden Namen wie `eth0`, `eth1` und `eht2` verwendet.
Dabei  war die Reihenfolge der "Entdeckung" der Schnittstellen durch das Betriebssystem massgebend.
=> Kann zu inkosistenz führen da nich immer gleich

## Neu
Die neue Benennung beginnt mit einem Schnittstellentyp:
- Ethernet -> `en`
- WLAN -> `wl`
- WWAN -> `ww`
Der Rest des Schnittstellennames basiert auf der Information, welche von der Serverfirmware bereitgestellt wird oder vom Standort des Geräts in der PCI-Topologie:
- `oN` -> Integriertes Gerät: Index $N$ -> wird durch Firmware bestimmt -> `eno1` 
- `sN` -> PCI-Hotplug: $N$ -> Nummer des Steckplatzes
- `pMsN` -> PIC-Gerät auf dem Bus $M$ im Steckplatz $N$
