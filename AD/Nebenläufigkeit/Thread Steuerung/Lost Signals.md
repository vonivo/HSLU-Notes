Über Objekte können sich [[Thread]] mit [[Wait]] und [[Notify]] Signale senden.
![[ThreadSignals.png]]

Dabei kann es vorkommen, dass Signale verloren gehen und ein [[Deadlock]] entsteht.
![[LostSignal.png]]

Verlorene Signale entstehen, weil:
- Die Signale von `notify` und `notifyAll` nicht gespeichert werden.
- Die zeitliche Abfolge zwischen `notify` und `wait` nicht stimmt:
	Wait wird nach notify aufgerufen -> Deadlock

Die Lösung für dieses Problem ist, die Speicherung der Signale. Dies kann über ein [[Semaphore]] gemacht werden.