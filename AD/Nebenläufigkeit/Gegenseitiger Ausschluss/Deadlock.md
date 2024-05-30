Ein Deadlock ist eine Verklemmung, bei der Threads gegenseitig darauf warten, dass ein kritischer Abschnitt verlassen wird und somit unendlich aufeinander warten.

![[Deadlock.png]]

Wenn Thread 1 `mehtode1`aufruft und Thread 2 nebenläufig `methode2` aufruft, kommt es zu einer Verklemmung:
![[Deadlock_2.png]]

## Deadlocks vermeinden
- [[Gegenseitiger Ausschluss#Monitorkenept#Nested Monitore|Nested Monitore]] vermeiden.
- Offene Aufrufe verwenden.
	Eine fremde Methode, die ausserhalb eines synchronisierten Bereichs aufgerufen wird, bezeichnet man als offenen Aufruf.
- Möglichst wenig Arbeit in einem synchronisiertem Block.
- In einem Synchronisiertem Abschnitt nie eine öffentliche oder geschützte Methode aufrufen, die dazu da ist um überschrieben zu werden.