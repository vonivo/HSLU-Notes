Das VLAN ist ein Virtuelles-Local-Area-Network. Es ermöglicht die Bildung von getrennten [[Netzwerk|Netzwerke]] auf gemeinsamer Hardware.

Dazu werden die Ports eines Switches einem Netz zugeordnet. Der [[Switch]] leitet jetzt nur Pakete selbe Netz weiter.
![[Pasted image 20250104105748.png]]
Pakete von einem blauen Port können jetzt nur an andere balue Ports weitergeleitet werden.

Das V-LAN kann auch HW übergreifend gewswitched werden, dafür werdend die beiden Geräte über den Trunk-Link verbunden.

Wichtig hier ist jedoch, dass da**s Ethernet-Frame mit dem V-LAN-Tag ergänzt** wird.

**Vorteile**
- erhöht Sicherheit durch weiter Abschottung
**Nachteile**
- Erhöhter Management bedarf.