Das [[Spanning Tree Protokoll]] hat sich im Laufe der Jahre entwickelt. Es gibt verschiedene Implementation von Rapid-Spanning-Tree (RSTP) und Multiple-Spanning-Tree MSTP.

State of the Art nach IEEE ist nun das RSTP-Protokoll.

Die momentane Cisco Implementation ist PVST+ (Per VLAN Basis). 
Um RSTP zu nutzen muss der Switch speziell konfiguriert werden.


| STP State  | RSTP State | RSTP Ports           | STP Port        |
| ---------- | ---------- | -------------------- | --------------- |
| Disabled   | Discarding | Root Port            | Root Port       |
| Blocking   | Discarding | Designated Port      | Designated Port |
| Listening  | Discarding | Backup Port (to HUB) | Designated Port |
| Learning   | Learning   | Alternate Port       | Blocked Port    |
| Forwarding | Forwarding |                      |                 |
