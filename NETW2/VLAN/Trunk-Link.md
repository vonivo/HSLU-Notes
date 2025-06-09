>[!Definition]
>Ein Trunk-Link ist ein Point-To-Point Link zwischen zwei Netzwerkgeräten (Swicht oder Router).

Cisco Geräte erlauben:
- Mehrere VLANs auf einem Trunk
- Ein VLAN über mehrere Geräte zu erstrecken
- Unterstützt 802.1Q Trunking.

![[Trunk-Link.png]]

Ist die [[NETW2/VLAN/VLAN|VLAN]]-Funktionlität aktiv, muss das Native-VLAN auf beiden Trunk-Seiten übereinstimmen.

## Konfiguration
```
S1(config-if)# switchport mode trunk
S1(config-if)# switchport trunk native vlan vlan-id
S1(config-if)# switchport trunk allowed vlan vlan-list (,-separated)
```

**Zurücksetzen**
```
S1(config-if)# no switchport trunk native vlan
S1(config-if)# no switchport trunk allowed vlan
S1(config-if)# no switchport mode access
```
