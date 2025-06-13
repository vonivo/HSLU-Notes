Das Cisco Discovery Protocol (CPD) ist ein proprietäres Layer 2 "Link Discovery" Protokoll und standardmässig aktiv.

CDP sendet automatisch und periodisch unverschlüsselte, unathentifizierte Broadcast, welche die IP-Adresse des Geräts, IOS-Softwareversion, Platform, Fähigkeiten und Native-VLAN enthalten.

Wenn ein Gerät ein CDP-Paket erhält, wird seine CDP-Datenbank aktualisiert.

=> Um CDP-Exploitation zu verhindern, sollte der Gebrauch von CDP auf Devices und Ports limitiert werden.
- Dekativieren von CDP auf allen Edge-Ports

**Konfiguration**
```
# global deaktivieren
S1(config)# no cdp run
# auf Port deaktivieren
S1(config-if)# no cdp enable
```