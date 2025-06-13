
## MAC-Address-Table Flooding
Alle [[Switch MAC-Adress Table]] haben eine fixe grösse.
Ein Angreifer bombardiert einen Switch so lange mit "Fake"-Source-MAC-Adresse, bis diese voll.
Wenn dass Passiert, behandelt ein Switch allen eingehenden Traffic als **unknown unicast** und flooded diesen an alle Ports im selben [[NETW2/VLAN/VLAN|VLAN]].

So kann der Angreifer alle Pakete erhalten.

=> Diese Attacken sind gefährlich, da so ein Overflow inert Sekunden gemacht werden kann und es auch andere Switches betroffen sein können.

=> Abhilfe schafft [[Port Security]].