x86 kennt 4 Levels von Privilegien.
Alle Userprogramme laufen nicht in privilegierten Levels, sondern im Ring 3.
Das OS braucht Zugriff auf HW daher läuft es im Ring 0.

![[Pasted image 20250107205104.png]]

Ein [[Hypervisor]] müsste nun zwischen HW und Ring 0 sitzen, damit er alle Instruktionen richtig ausführen kann, oder er müsste eine spezielle API im Hypervisor mit speziellem Befehlssatz.