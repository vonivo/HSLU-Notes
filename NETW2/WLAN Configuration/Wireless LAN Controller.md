Einige Access Points benötigen einen WLC um ihre Konfiguration zu erhalten. Diese AP werden **lightweight Acces Points (LAP)** , da sie keine initiale Konfiguration benötigen.

LAPs nutzen das Lightweight Access Point Protokoll um mit dem WLC zu kommunizieren.

>[!info]
>WLC sind besonders nützlich, wenn ser viele APs benötigt werden.

- Jeder physische Port eines WLCs kann mehrere APs und WLANs unterstützen.
- Diese Ports sind ähnlich zu einem [[Trunk-Link]]
- Jeder AP unterstützt mehere WLANs.

**Standardkonfiguration**
1. WLAN erstellen.
2. WAN einschalten.
3. Interface auswählen.
4. WLAN sichern.
5. Funktionalität überprüfen.
6. WLAN überwachen
7. Client Informationen abrufen.

Jedes WLAN auf dem WLC benötigt ein eigenes Virtual-Interface (VLAN Interface)