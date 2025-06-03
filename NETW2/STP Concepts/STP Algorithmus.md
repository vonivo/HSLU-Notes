Der STP-Algorithmus wurde von Radia Perlman erfunden. Er erstellt eine Loop-Freies Netzwerk, indem eine Root-Bridge selektiert wird und alle anderen Switches einen "single least Cost"-Path zur Root-Bridge haben.

Das STP Protokoll blockiert gewisse Ports strategisch, um einen Loop zu vermeiden. Diese Ports können im Fehlerfall wieder entblockt werden.

**Konzept**
1. Root-Bridge Selection
2. Redundante Pfäde blockieren. -> Nur ein logischen Pfad zu allen Geräten in Netz
3. Loop-Freie Topologie erstellen -> Jeder Switch hat einen Weg zur Root-Bridge
4. Rekalkulierung im Fehlerfall.

**Detaillierter Ablauf**
1. Root-Bridge selektieren
2. Root-Ports selektieren
3. Designated-Ports selektieren
4. Alternative Ports selektieren

Während dem STP Protokoll werden Bridge Protocol Data Units (BPDUs) versendet (2s Takt) um Informationen zu verteilen.

## Root-Bridge Selektion
**Root-Bridge-Priorität:** 0-61440 in 4096 Inkremente (Default: 32768). Tiefer = Besser
**Extended-System-ID**: Dezimal-Zahl für VLAN-ID, wird zur Priorität hinzugefügt.
**MAC-Adress**: In extremis-> Switch mit tiefster MAC.

Anfänglich deklariert sich jeder Switch als Root-Bridge. Nach und nach aktualisiert sich das mit der tiefsten Roo-Bridge-ID

## Root-Port Selektieren
Nachdem die Root-Bridge selektiert ist, bestimmt jeder Switch ein Root-Port. Der Root-Port ist der Port welcher am "nächsten" (tiefste Kosten) zur Root-Bridge ist.
### Root-Path-Costs 
Nach der Root-Bridge-Selektion startet die Analyse des besten Pfades zur Root-Bridge. Die "Internal-Root-Path-Cost" ist die Summe aller Port-Costs bis zur Root-Bridge.

Alle anderen Ports werden blockiert.

**Bestimen der Kosten**
Ein Switch empfängt eine BPDU mit einer Root Path Cost. Er addiert die Port-Kosten (Path Cost) seines Eingangsports hinzu und prüft, ob das Ergebnis kleiner ist als sein bisheriger Root Path. Wenn ja, aktualisiert er seine Root-Information.

| Link Spped | STP Cost | RSTP Cost |
| ---------- | -------- | --------- |
| 10 Gbps    | 2        | 2,000     |
| 1 Gbps     | 4        | 20,000    |
| 100 Mbps   | 19       | 200,000   |
| 10 Mbps    | 100      | 2,000,000 |
Tie-Breaker:
1. STP-Cost (Link Speed)
2. BID
3. Port-Priorität (Konfiguriert auf Switch)
4. Port-Number

## Bestimmen der Desiganted Ports
- Jeder Port zu einem Endgerät
- Jeder Port gegenüber einem Root-Port
- Jeder Port-Zwischen 2 Switches mit der Tiefsten Root-Path-Cost
-> alle anderen Ports Blocked oder Alternate-Ports


# STP-States

| Port-State | BPDU             | MAC-Address Table | Forwading? |
| ---------- | ---------------- | ----------------- | ---------- |
| Blocking   | Receive          | No update         | no         |
| Listening  | Receive and send | No update         | no         |
| Learning   | Receive and send | Updating Table    | no         |
| Forwarding | Receive and send | Updating Table    | yes        |
| Disabled   | none             | no update         | no         |
