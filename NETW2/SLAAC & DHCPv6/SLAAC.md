Nicht jedes Netzwerk hat zugang zu einem DHCP. Daher ermöglicht SLAAC (Stateles-Address-Autoconfiguration) eine [[IPv6 GUA Assignment|GUA]] zu erhalten.

SLAAC sendet alle 200s ein RA-Paket welches informationen zur erstellung der GUA enthalten.

Ebenfals reagiert ein Router auf RS-Messages mit RAs. Die RS Messages werden an `ff02::2` versendet.

**Adresse Generieren**
1. 64-bit Subnet info (von router oder DHCP)
2. 64-bit Interface ID
	1. **Random-Generated**: Zufällig nich von MAC-Abhängig -> ändert Regelmässig
	2. **EUI-64**: 48-bit MAC wird auf 64-bit ergänzt (`FF-FE` in Mitte)-> Rückverfolgbar
	3. **Stable privacy addresses**: Ändert pro Netzwerk. Meist hash von verschiedenen Parameter. Nich überall gelich implementiert.