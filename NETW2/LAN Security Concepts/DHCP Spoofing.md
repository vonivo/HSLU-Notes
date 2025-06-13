
## DHCP Starvation
Ziel dieser Attacke ist es, eine DoS für Clients zu erstelllen.
DHCP-Starvation benötigt ein Tool, z.B. Gobbler, welches alle Verfügbaren IP-Adressen des DHCP-Pools mietet.

Dabei werden extrem viele DHCP-Discovery und Request mit tampered MAC-Adressen durchgeführt.

Dies Führt dazu, dass ein valider Client keine IP-Adresse mehr bekommt.


## DHCP-Spoofing
DHCP-Spoofing ist, wenn ein Rouge-DHCP existiert und falsche IP-Konfigurationen
bereitstellt;
- **Falscher Default-Gateway.** -> Erlaubt [[MITM]]
- **Falscher DNS**-> Falsch DNS-Records leiten User auf falsche Seiten weiter.
- **Falsche IP** -> Server kann eine Internet-Verbindung herstellen.
