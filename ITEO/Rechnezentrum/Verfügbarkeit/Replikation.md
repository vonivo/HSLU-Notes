Die Replikation ist das Verfahren, um Daten von einem Medium auf ein anderes zu spiegeln.
Die Replikation wird eingesetzt, um die [[Verfügbarkeit]] eines [[Rechenzentrum]] zu erhöhen.

Um die primäre Datenbank nicht andauernd mit der Replikation zu belasten wird ein kombinierter Ansatz aus synchroner und Asynchroner Replikation benutzt.

![[Pasted image 20250103153550.png]]
1. Die Daten werden lokal im Rechenzentrum A auf ein abgeschotteten Speicher Repliziert.
2. Die Daten auf den abgeschotteten Speicher werden asynchron auf das Rechenzentrum B repliziert.

Wenn alle Daten zu 100% synchronisiert sind, kann ein [[Failover Cluster|Fail-Over]] durchgeführt werden.