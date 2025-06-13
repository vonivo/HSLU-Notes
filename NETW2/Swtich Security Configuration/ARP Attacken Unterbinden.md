ARP-Spoofing und ARP-Poisoning wird mittels [[DHCP Snooping|DHCP-Spoofing]] **Dynamic ARP Inspection (DAI)** verhindert.

Dadruch werden keine schädlichen ARP-Nachrichten mehr propagiert.

**Konfiguration**
DHCP-Snooping ist konfiguriert
```
S1(config)# ip arp inspection vlan ID
```


**Trusted Port hinzufügen**
```
S1(config-if)# ip arp inspection trust
```

**Modi**
- **dst-mac**: Überprüft dest MAC. in Ethernet Header mit Target MAC in ARP-Body.
- **src-mac** Überprüft src. MAC in Ethernet Header mit sender MAC in ARP-Body
- **ip:**  Überprüft ARP-Body auf ungültige IP (0.0.0.0, 255.255.255.255, multicasts)
```
S1(config)# ip arp inspection validate [MODI ','-separated]
```