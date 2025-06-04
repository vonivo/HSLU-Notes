Da die durch [[SLAAC]] generiert [[NETW2/SLAAC & DHCPv6/IPv6|IPv6]] nicht immer eindeutig ist, wird DAD verwendet.
- Host sendet ICMPv6 Neighbor Solicitation (NS) Nachricht mit dem letzten Teil seiner IP.
- Wenn er keine Antwort bekommt => i.O, ansonsten neu wird Adresse neu generiert.

=> DAD nicht wirklich notwendig da [[NETW2/SLAAC & DHCPv6/IPv6|IPv6]] sehr kollisionsresistent ist.
