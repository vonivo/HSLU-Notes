Standardmässig versendet ein IPv6-enabled Router periodisch ICMPv6 RAs (Router-Advertisment).

Diese RAs vereinfachen den [[IPv6]] Konfigurationsprozess des Clients.

Eine GUA kann auf verschiedene Arten erstellt werden:
![[GUA_Assignment.png]]
Welche Variante gewählt wird, hängt von der RA-Message ab:

- **A-Flag:** Sinalisiert benutzung von SLAAC
- **O-Flag:** Singalisiert die zusätzliche Verwendung von DHCP
- **M-Flag:** Signalisiert stateful DHCP

| Falgs        | Art                    |
| ------------ | ---------------------- |
| A=1, O=0,M=0 | SLAAC über RA          |
| A=1,O=1, M=0 | SLAAC über RA und DHCP |
| A=0, M=1     | Satefull DHCPv6        |

