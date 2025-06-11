DHCPv4 ([[DHCP]]) läfut in einer Client / Server umgebung, bei auch ein Cisco-Router als kleiner DHCP-Server fungieren kann.

- Wenn ein Client sich auf ein Netzwerk verbindet, bekommt er eine [[IP-Adresse]]. Diese Adresse ist gültig, bis die `lease`-Time abläuft.
- Die `lease`-Time stellt sicher, dass ein Client welcher das Netz verlässt (PowerOff) die Adresse nicht unendlich behält.

**Ablauf**
1. Client -> Server: DHCP Discover (broadcast)
2. Server -> Client: DHCP Offer (unicast)
3. Server -> Client: DHCP Request (broadcast)
4. Server -> Client: DHCP Acknowledgment (unicast)

Der Client kommuniziert immer im Broadcast-Modus mit dem Server, falls mehrere DHCPs in selben Netz sind .


**Renew**
1. Bei $50\%$ sendet der Client ein **unicast** DHCP Request direkt zum Server.
2. Erhält er keine Antwort sendet er bei $77\%$ ein **broadcast** DHCP Request.
3. Server -> Client: DHCP Acknowledgment (unicast)

## Konfiguration
1. Adressen aus Pool exkludieren (Range low high)
2. Pool-Name spezifizieren
3. DHCP-Pool Konfigurieren
	1. Default Router
	2. DNS
	3. Domain-Name
	4. lease
	5. netbios-name-server
	6. Netzwerk

```
R1(config)# ip dhcp excluded-adress 192.168.10.1 - 192.168.10.9
R1(config)# ip dhcp excluded-address 192.168.10.254
R1(config)# dhcp pool LAN-POOL-1
R1(dhcp-config)# network 192.168.10.0 255.255.255.0
R1(dhcp-config)# default-router 192.168.10.1
R1(dhcp-config)# dns-server 192.168.11.5
R1(dhcp-config)# domain-name example.com
```
**Einschalten / Ausschalten**
```
R1(config)# service dhcp
R1(config)# no service dhcp
```

**Verifizierungs Kommandos:**
```
R1# show running-config | setcion dhcp
R1# show ip dhcp binding
R1# show ip dhcp server statistics
```


## Relay
Wenn sich der DHCP-Server ausserhalb des Netzwerks befindet, kann der Router als Relay fungieren:

**Konfiguration**
```
R1(config)# interface g0/0/0
R1(config-if)# ip helper-address 192..168.11.6
```

## Client
Es gibt Fälle in denen ein Router-Interface auch eine dynamische IP-Zuweisung benötigt. z.B. bei einem Provider. Dafür kann er als DHCPv4 Client konfiguriert werden.

**Konfiguration**
```
R1(config)# interface g0/0/0
R1(config)# ip adress dhcp
```
