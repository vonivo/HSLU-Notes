Ein Spanning-Tree-Protokoll ist ein Loop-Prevention Netzwerk-Protokoll welches Redundanzen auf Layer 2 erlaubt ohne Loops zu verursachen.
![[STP.png]]
Bei einem Ausfall einer "Leitung" wird ein vorher blockierte Leitung wieder freigeschaltet.

Wenn ein Layer2-Loop existiert kann dies zu:
- MAC adress table instabilit,
- Link saturation
- hoher CPU Auslastung
führen

Layer 2 Ethernet hat kein Protokoll welches endloses Weiterleiten verhindert (Layer3: TTL). Daher existieren STP Protokolle. 