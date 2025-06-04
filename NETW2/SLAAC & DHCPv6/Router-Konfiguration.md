[[NETW2/SLAAC & DHCPv6/IPv6|IPv6]] auf einem Cisco-Gerät konfigurieren:
```
R1(config)# ipv6 unicast-routing
```

Wird dieser Befehl ausgeführt, werden alle Interfaces zur IPv6 all-routers Gruppe hinzugefügt `ff02::2` und senden [[IPv6 GUA Assignment|RAs]] (falls Interface ein IPv6 hat) (Standard: A=1,O=0,M=0)

**O-Flag konfigurieren**
```
R1(config-if)# ipv6 nd other-config-flag
```

**M-Falg konfigurieren**
```
R1(config-if)# ipv6 nd managed-config-flag
```

