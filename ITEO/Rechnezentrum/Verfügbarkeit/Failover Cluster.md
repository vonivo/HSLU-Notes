Das Failover Cluster ist ein Mechanismus um die [[Verfügbarkeit]] im [[Rechenzentrum]] zu erhöhen.
![[Pasted image 20250103152330.png]]
Der Zugriff auf die Daten erfolgt über eine **virtuelle IP**
- Im Standardfall wird der **Host 1** angesprochen
- Gibt es einen Fehler wird die virtuelle IP auf **Host 2** umgemappt.
- Durch die **Heart-Beat** Direktverbindung merkt der Host 2, dass Host 1 gefailed ist und kann nun die Funktionalität übernehmen.

