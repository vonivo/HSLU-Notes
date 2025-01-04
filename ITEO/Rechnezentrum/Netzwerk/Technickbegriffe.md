## DNS
Das Domain-Name-System ist für die Auflösung für URLs zu IP-Adressen verantwortlich.

## IPAM
Das IP-Address-Management ist für die Verwaltung der IP-Addressen im [[Netzwerk]] verantwortlich. (z.B. MS Service)

## DHCP
Das Dynamic-Host-Configuration-Protocol ist dafür verantwortlich, dass Clients automatisch eine IP-Adresse, Netzmaske, Default-Gateway usw. bekommen.

## NAP und NAC
Die Network-Access-Protection und Network-Access-Control definiere, in welches Netzwerk ein Gerät darf.
So kann z.B. ein MAC-Wihtelisting gemacht werden oder ein unbekanntes Gerät wird zuerst in ein Quarantäne-Netzwerk verschoben. Erst wenn es alle Anforderungen (z.B. Virenschutz, gültige Zertifikate oder Updates) erfüllt, wird es in das richte Netzwerk verschoben.

## MPSL
Multiprotocol Label Switching ist eine VPN-ähnliche Struktur zur Verbindung von zusammengehörigen Netzwerken ohne Rücksicht auf IP-Segmenten.

Dabei wird die Paketvermittlung durch den [[Provider]] aufgrund von Labels in den Paketen vorgenommen.

Tunneling auf Layer 2

## Class of Service
Mit der Class of Service kann bestimmt werden, wie viel Bandbreite der Leitung für einzelnen Klassen genutzt werden soll (z.B 300 MBit/s für Stream, 200 MBit/s für File Transfer etc.)