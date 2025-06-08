Damit ein Switch über Remote-Management-Access verwaltet werden kann, benötigt er:
- IP Adresse und Subnetzmaske
- Default Gateway
- Switch Virtual Interface (SVI)

Standardmässig wird ein Switch über [[VLAN]] 1 konfiguriert. Dies sollte jedoch geändert werden.

Ein SVI erscheint erst als Up/Up wenn ein Gerät an einem VLAN 99 Port angeschlossen ist und das VLAN existiert.

**SVI-Konfigurieren**
```
S1# configure terminal
S1(config)# interface vlan 99
S1(config-if)# ip address 172.17.99.11 255.255.255.0
S1(config-if)# ipv6 address 2001:db8:acad:99::1/64
S1(config-if)# no shutdown
S1(config-if)# end
S1# copy running-config startup-config
```

**Default Gateway Konfigurieren:**
```
S1# configure terminal
S1(config)# ip default-gateway 172.17.99.1
```

## Sicherer Remote Access
**Telnet**: Nutzt unverschlüsselte Übertragung -> nicht mehr verwenden.
**[[OpenSSH|SSH]]**: Nutzt verschlüsselte Kommunikation -> sicher.

**Überprüfen ob SSH-Fähig:**
```
S1# show version
Cisco IOS Software, C2960 Software (C2960-LANBASEK9-M), Version15.0(2)SE7, RELEASE Software
```
-> Wenn `K9` ersichtilich ist SSH unterstützt.

**Ablauf**
1. SSH-Fähigkeit überprpfen
2. IP Domain-Name konfigurieren `S1(config)# ip domain-name <name>`
3. RSA-Keys definieren:`S1(config)# crypto key generate rsa`
4. User-Authentication konfigurieren: ``S1(config)# username <username> secret <password>`
5. vty-Lines konfigurieren: `S1(line-0)# transport input ssh` und `S1(line-o )# login loca`
