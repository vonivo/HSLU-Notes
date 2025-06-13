## VLAN Hopping
Eine [[VLAN]]-Hopping Attacke erlabut es Taffic von VLAN $A$ von einem anderen VLAN $B$ aus zu sehen.

Um dies zu erreichen, konfiguriert ein Angreifer einen Host als **[[Trunk-Link]]** um das [[Dynamic Trunking Protocol]] auszunutzen (default auf vielen Geräten).

Der Host Spooft dann 802.1Q Packete um ein automatisches Trunking zu initialisieren. Falls dies funktioniert wird ein [[Trunk-Link]] hergestellt und der Angreifer kann auf alle VLANs zugreifen.

## Double Tagging
Ein Angreifer kann in spezifischen Situationen ein 802.Q-Tag in einem schon getaggeten Paket embedden. Dieses Erlaubt einem Angreifer Pakete an ein anderes VLAN zu senden.

1. Angreifer sendet ein double-tagge 802.1Q-Frame zum Switch. Der äusser Header enthält den VLAN-Tag des Angreifers welcher gleich ist wie das Native-VLAN.
2. Das Frame kommt zum Switch und der Switch sieht, dass es für das Native-VLAN bestimmt.
3. Der Switch entfernt den VLAN-Tag um leitete das Paket zu allen Native-VLAN Ports. => Das Frame wird nicht mehr re-tagged, da es sich um das Native-VLAN handelt. Der innere VLAN-Tag ist jedoch immer noch intakt.
4. Das Frame kommt beim 2. Switch an, welcher nicht weiss, dass das Paket für das Native-VLAN bestimmt ist und leitet das Packet an das VLAN weiter welches im inneren Tag spezifiziert ist.

Funktioniert nur:
- Wenn der Angreifer sich im Native-VLAN befindet.
- Nur unidirektional

**Abhilfe**
- Ausschalten von [[Dynamic Trunking Protocol]]
- Ausschalten von Auto-Trunking, nur manuelle Konfiguration
- Native-VLAN nur für Trunk-Links nutzen.