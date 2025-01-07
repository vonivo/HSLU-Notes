![[Pasted image 20250106201853.png]]
Die Variable $X$ befindet sich in den Caches von $P_{1}$ und $P_{2}$.

Wass passiert wenn $P_{1}$ die Variable nun Ändernt?

## Write Trhough Cache
Beim Write Through Cache wird $X$ direkt im Hauptspeicher verändert. Jedoch weiss $P_{2}$ immer noch nicht, dass sich diese verändert hat.

![[Pasted image 20250106202034.png]]
## Writeback Cache
Beim Writeback Cache wird der Hauptspeicher nicht sofort verändert, daher kann $P_{2}$ immer noch den falschen Wert auslesen.
![[Pasted image 20250106202349.png]]

## Wie kann das Problem gelöst werden?
Grundsätzlich existieren zwei Wege:
1. Cache-Protokoll:
	1. [[Snoopy]]
	2. [[Directory]]
2. Verwendung von gemeinsamen Cache.


