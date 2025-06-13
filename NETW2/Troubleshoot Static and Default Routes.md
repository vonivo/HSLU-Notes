Ein Netzwerk kann wegen vieler Sachen fehlschlagen:
- Interface Fehler.
- Service Provider unterbricht die Verbindung.
- Links voll ausgelastet.
- Falsche Konfiguration

**Trouble Shooting Befehle**

| Befehl                   | Beschreibung                                                                   |
| ------------------------ | ------------------------------------------------------------------------------ |
| `ping`                   | Layer3 Konnektivität überprüfen                                                |
| `traceroute`             | Pfad zu Ziel überprüfen.<br>Nutzt ICMP echo-reply-messaged um Hops zu erkennen |
| `show ip route`          | IP-Routingtabelle anzeigen                                                     |
| `show ip interface brie` | Device-Interface-Status abfragen.                                              |
| `show cdp neighbors`     | Direktverbunden Cisco Geräte anzeigen                                          |
