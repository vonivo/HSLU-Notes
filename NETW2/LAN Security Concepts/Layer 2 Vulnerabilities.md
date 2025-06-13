>[!Warning]
>Der Layer 2 wird generell als der schwächste Layer angesehen.

**Mögliche Angriffe auf Layer 2**

| Category                    | Beispiel                   |
| --------------------------- | -------------------------- |
| [[MAC Table Attacks]]       | MAC-Flooding               |
| [[VLAN Attacks]]            | VLAN hopping               |
| [[DHCP Spoofing]]           | DHCP Starvation            |
| [[ARP Attacks]]             | ARTP spoofing              |
| [[Adress Spoofing Attacks]] | MAC und IP-Spoofing        |
| [[STP Attacks]]             | Spanning Tree manipulation |

**Lösungen und Techniken**

| Lösung                            | Beschreibung                                                                 |
| --------------------------------- | ---------------------------------------------------------------------------- |
| [[Port Security]]                 | Verhindert viele Attacken inklusive MAC-Address-Flooding und DHCP-Starvation |
| [[DHCP Snooping]]                 | Verhindert DHCP Starvation und DHCP spoofing                                 |
| [[ARP Attacken Unterbinden\|DAI]] | Verhindert ARP-Spoofing und ARP poisoning                                    |
| [[IP Surce Guard]]                | Verhindert MAC- und IP-Spoofing                                              |
