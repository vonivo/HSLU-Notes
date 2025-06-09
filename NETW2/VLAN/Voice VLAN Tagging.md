Ein Cisco VoIP-Phone ist ein 3-Port Switch und kann selbst taggen.
Dabei setzt es Cost-of-Service (CoS)-Parameter für Layer 2

Dabei gibt es folgende Modi:

| Traffic     | Tags                                     |
| ----------- | ---------------------------------------- |
| Voice-VLAN  | Tagged mit dem Layer 2 CoS parameter     |
| Access VLAN | Kann auch mit CoS-Parameter getaggt sein |
| Access VLAN | ist nich tagged                          |
![[VoIP.png]]
## Konfiguration
```
S1(config)# vlan 20
S1(config-vlan)# name DATA
S1(config)# vlan 150
S1(config-vlan)# name VOICE
S1(config-if)# switchport mode access
S1(config-if)# switchport access vlan 20
S1(config-if)# mls qos trust cos
S1(config-if)# switchport voice vlan 150
```
