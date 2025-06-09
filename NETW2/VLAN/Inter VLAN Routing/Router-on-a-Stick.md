Router-on-a-Stick benötigti im Gegensatz zu [[Legacy Inter-VLAN Routing]] nur noch ein physisches Interface.

- Das Router-Interface ist dabei als `802.1Q trunk` konfiguriert und auch zu einem - `trunk`-Port auf dem Switch verbunden. [[Trunk-Link]].
- Pro VLAN wird ein **SubInterface** auf dem Router erstellt, welches mit dem physischen Port verbunden ist. Jedes SubInterface besitzt eine eigene IP-Adresse und [[NETW2/VLAN/VLAN|VLAN]] assignment.

VLAN-Tagged Traffic wird nun über das physische Interface entgegengenommen und zum korrekten SubInterface weitergeleitet. Der Router bestimmt jetzt das Ausgangs-Interface, wenn das Ausgangs-Interface ein `802.1Q` ist, wird das Paket mit einem VLAN-Tag versehen und versandt.

![[Router-On-A-Stick.png]]

## Konfiguration
1. VLANs erstellen und benennen
2. Management Interfaces erstellen
3. Access-Ports konfigurieren
4. Trunk-Ports konfigurieren

**Beispiel**
```
R1(config)# interface g0/0/1.10  # .ID ist subInterface-ID
R1(config-if)# encapsulation dot1Q 10 # 10 -> VLAN ID
R1(config-if)# ip add 192.168.10.1
R1(config-if)# exit
R1(config)# interface g0/0/1.20  # .ID ist subInterface-ID
R1(config-if)# encapsulation dot1Q 20 # 10 -> VLAN ID
R1(config-if)# ip add 192.168.20.1
R1(config-if)# exit
R1(config)# interface g0/0/1.99  # .ID ist subInterface-ID
R1(config-if)# encapsulation dot1Q 99 # 10 -> VLAN ID
R1(config-if)# ip add 192.168.99.1
R1(config-if)# exit
R1(config)# interface g0/0/1
R1(config-if)# no shutdown
```