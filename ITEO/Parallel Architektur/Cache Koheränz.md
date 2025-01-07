![[Pasted image 20250106201853.png]]
Die Variable $X$ befindet sich in den Caches von $P_{1}$ und $P_{2}$.

Wass passiert wenn $P_{1}$ die Variable nun Ändernt?

## Write Trhough Cache
Beim Write Through Cache wird $X$ direkt im Hauptspeicher verändert. Jedoch weiss $P_{2}$ immer noch nicht, dass sich diese verändert hat.

![[Pasted image 20250106202034.png]]
## Writeback Cache
Beim Writeback Cache wird der Hauptspeicher nicht sofort verändert, daher kann $P_{2}$ immer noch den falschen Wert auslesen.
![[Pasted image 20250106202349.png]]

Wie kann nun gelöst, werden, dass alle Caches denselben Stand haben?
[[Snoopy]]
[[Directory]]

