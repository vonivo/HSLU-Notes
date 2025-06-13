## SSID Cloaking
[[AP]]s und [[Wireless Router]] erlauben es den SSID-Beacon zu deaktiveren. Dadurch müssen sich Clients aktiv zum Router verbinden.

## MAC-Address Filtering
Administratoren können ähnlich wie bei [[Port Security]] MAC-Adressen whitelisten.


## Open System Authentication
- Kein Passwort nötig.
- Clients selbst für Sicherheit verantwortlich. z.B. über VPN

## Shared Key Authentication
Stellt Mechanismen wie WEP, WPA, WPA2 und WPA3 zur Verfügung um Benutzer zu authentifizieren und um die Kommunikation zwischen Client und AP zu verschlüsseln.

Jedoch muss das Passwort vorher geteilt werden.


| Authentication Methode             | Beschreibung                                                                                                                                                                   |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Wired Equivalent Privacy (**WEP**) | Original 802.11 spezifikation. Benutzt Rives Cipher 4 (RC4) Verschlüsselung mit einem statischen Key.<br>**Nich mehr empfohlen**                                               |
| Wi-FI Protected Access (**WPA**)   | Wi-Fi Alliance Standard welches WEP benutzt, die Daten jedoch mit dem viel stärkeren Temporal Key Integrity Protokol verschlüsselt. (TKIP wechselt schlüssel nach jedem Paket) |
| WPA2                               | Nutzt AES für die Verschlüsselung.                                                                                                                                             |
| WPA3                               | Neuster standard, braucht noch PMF (Protected Management Frames)                                                                                                               |

## WPA2 Authentication-Modes
**Personal**
Angedacht für zu Hause.
Benutzer werden anhand eines Pre-Shared Key authentifiziert.

**Enterprise**
Für Firmen.
Benötigt einen RADIUS-Server. Das Gerät muss von RADIUS-Server authentisiert werden und der Benutzer muss sich via 802.1X Standard, welches Extensible Authentication Protocol (EAP) nutzt, authentisieren.

## WPA3 Modes
**WPA3-Personal**
Minder Brute-Force mit Simultaneous Authentication of Equals. (SAE)

**WPA3 Enterprise**
Nutzt 802.1X/EAP Authentifikation. Verlangt einen 192-bit Krypto-Suite und verhindert das mischen von Security-Prokollen für vorherige 802.11 Standards

**IoT Onboarding**
Nutzt Device Provisioning Protocol (DPP) um IoT Geräte zu onboarden.