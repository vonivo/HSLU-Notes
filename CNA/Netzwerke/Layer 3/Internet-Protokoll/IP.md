IP (Internet Protokoll) ist das Protokoll des [[Network-Layer]]. Das IP-Protokoll ist seit seinem Ursprung (1974) für [[Internetworking]] ausgelegt.

# IP-Header
In Header eines IPv4-Pakets sieht folgendermassen aus:
![[IPv4Header.png]]
Ein IPv4-Header besitzt meistens $4\times5$-Bytes und ist somit 20-Bytes gross (kann jedoch bis zu 60 Bytes werden).

Der Header setzt sich zusammen aus:
- Version
- IHL -> IP-Header Length
- Diensttyp -> Vorrang (Delay/Druchsatz, Zuverlässigkeit)
- Gesamtlänge des IP-Pakets (max 65'535 Bytes)
- Identifikation: kennzeichnet Fragmente eines Datagrams
- Fragment-Offset
- Lebensspanne
- Protokoll
- Prüfsumme
- Quelladresse
- Zieladresse

# Fragmentierung
Das Aufteilen eines grossen Pakets in kleinere IP-Pakete nennt man **Fragmentierung**. 
Fragmentierung wird ausgeführt, da die maximale Nutzdatengrössen (MTU) einzelner [[Netzwerke]] unterschiedlich sein kann.

## Transparente Fragmentierung
Bei der Transparenten Fragmentierung wird ein fragmentiertes Paket bei jeder Zwischentation wieder defragmentiert und dann weitergesendet (allenfalls nochmals fragmentiert)
![[Transparent_Fragmentation.png]]

## Intransparente Fragmentierung
Bei der intransparenten Fragmentierung wird ein fragmentiertes Paket erst wieder beim Zielhost zusammengesetzt.
![[Intransparent_fragmentation.png]]