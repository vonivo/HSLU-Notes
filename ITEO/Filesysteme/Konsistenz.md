Um Konsistenz von Daten auf einer Disk wiederherzustellen gibt es verschiedene Möglichkeiten:
- Fsck oder chkdsk: Bei Anwendung auf grosse Volumen kann dies > 72 Studen in Anspruch nehmen.
- CoW (Copy on Write) und RoW (Redirect on Write)

Mit [[ZFS]] wird über die Hashes sichergestellt, dass wir jederzeit konsitente Date haben.

## Copy on Write
Die alten Daten werden beim Write in einen neuen Speicherblock kopiert. Die Speicherblöcke der alten Daten werden überschrieben.
Die alten Daten können für [[Snapshot]] verwendet werden oder werden gelöscht, falls die Verkettung fertig angepasst wurde.
![[Pasted image 20250108164327.png]]

## Redirect on Write
Wenn bestehende Datenblöcke überschrieben werden sollen, werden die Daten in einen neuen Block geschrieben (redirect). Der Originalblock bleibt unverändert. Erst nach erfolgreicher Anpassung der Verkettung darf der Originalblock angepasst werden.
![[Pasted image 20250108164522.png]]
Bei [[ZFS]] wird oft von CoW gesprochen, aber es wird eher ein RoWverwednet:  

- Zfs verwendet rellocate or redirect on Write
- Blöcke mit Aktiven Daten werden nie überschreiben
- Der Intent Log (ZIL) wird verwendet wenn synchrone Schreibsemantik verlangt wird (Schreibabsicht wird im Log protokolliert -> verstecktes Journalling auf Atomic Operation Eben
![[Pasted image 20250108165430.png]]
## Silent Corruption
Sielnt Corruption ist die Stille Corruption bei einem Raid 1.  
Auf einem Speichergerät sind die Daten inkonsistent auf dem Anderen aber noch Konsisten. Dadurch wird der Lesevorgang inkonsisten (Zufällig von welcher Platte gelesen wird)
![[Pasted image 20250108165747.png]]
Bei ZFS werden durch die Hashes kaputte Daten sofort erkannt und dann direkt korrigiert.
![[Pasted image 20250108165848.png]]
