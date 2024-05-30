[[Thread|Java-Threads]] durchlaufen während der Verwendung verschiedene Zustände:
![[Thread_simple_lifecycle.png]]
- Ein Thread kann **nur einmal** gestartet werden.
- Mit `isAlive()` kann festgestellt werden, ob sich ein Thread im `RUNNABLE` Zustand befindet.

Durch [[AD/Nebenläufigkeit/Thread/Interrupt|Interrupts]] entstehen folgender neuer Lebenszyklus:
![[Thread_lifecycle_interrupt.png]]
- Durch einen [[AD/Nebenläufigkeit/Thread/Interrupt|Interrupt]] können die Zustände `WAITING` und `TIMED_WAITING` verlassen werden.
- `BLOCKED` kann nicht verlassen werden.


Durch den [[Gegenseitiger Ausschluss|gegenseitigen Ausschluss]] wird ein neuer Zustand `Object locj-pool` benötigt.
![[ThreadLifecycle_Lockpool.png]]