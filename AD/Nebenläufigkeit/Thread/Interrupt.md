Die [[Methode]] `interrupt` setzt ein **Interrupt-Flag** des [[Thread]] und signalisiert, dass eine **Unterbrechungsanforderung** gestellt wurde. (Die Methode löst jedoch keine [[Exceptionhandling|Exception]]) aus.

Mittels `isInterrupted()` kann der Interrupt-Status abgefragt werden.

Mittels `Thread.interrupted()` wird der Interrupt-Status des **aktuellen Threads** ausgelesen, setzt das Falg jedoch danach auf `false`.



- Befindet sich ein Thread in einer **blockierten Wartemethode**, wird der Thread durch`interrupt()` geweckt.
- Stösst der Thread im weiteren Verlauf auf eine Wartemethode, wird diese gleich nach Betreten wieder verlassen.
- In beiden Fällen wird eine `InterruptedException` ausgelöst.

Folgende Methoden können eine `InterruptedException` auslösen:
- `sleep`
- `join`
- `wait`

>[!warning]
>Durch das Auslösen einer `InterruptedException` wird das Interrupt-Flag auf false gesetzt.
>$\implies$ ggf. muss Flag explizit wieder gesetzt werden.

## Reaktion auf `InterruptedException`
- Exception abfangen und terminieren.
	- Üblich mindestens eine Medlung zu loggen.
	- Im catch-Teil Beenden einleiten: Nochmals `interruptUI` aufrufen um Falg zu setzen, und über `return` beenden.
- Excpetion abfangen und eventuell nicht terminieren, wenn angefangen Arbeitsphasen beendet werden sollen.
