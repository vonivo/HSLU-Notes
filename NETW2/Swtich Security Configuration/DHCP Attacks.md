Mithilfe von Tools wie Gobbler kann eine DHCP-Starvation und somit ein DoS erreicht werden.

Der erste schritt um dies zu Verhinder ist Port-Security zu konfigurieren

Der zweite ist DHCP-Spoofing zu konfigurieren
DHCP Spoofing konfiguriert ein DHCP-Rate-Limite in der Sekunde.

**Konfiguration**
```
S1(config)# ip dhcp snooping
S1(config-if) ip dhcp snooping trust
S1(config-if) ip dhcp snooping limit rate
S1(config)# ip dhcp snooping vlan v,l,a,n,s
```