>[!Definition]
>Eine **Transaktion** ist eine Atomare Einheit von Ausführungen: Entwerder alles oder nichts.

Wird von vieler Software unterstützt:
- Datenbanken
- [[Persistente Kommunikation|Message Orienten Middleware]]
- etc.

**Ablauf**
1. Transaktion wird gestartet.
2. Mehrere zusammengehörige Aktionen werden innerhalb der Transaktion ausgeführt.
3. Transaktion entweder
	1. erfolgreich Abschliessen (commit).
	2. abbrechen (rollback)

```java
void transferAmount(Account from, Account to, int amount) {
	try {
		accountDb.beginTransaction(); // Beginne Transaktion
		
		accountDb.debit(from, amount); 
		accountDb.credit(to, amount); 
		
		accountDb.commit(); // Transaktion abschliessen
	} catch (Throwable t) {
		accountDb.rollback(); // Rollback falls fehler
		throw t;
	}
}
```


## Verteilte Transaktion
Für ein Bankensystem wird eine Konten-DB und eine Audit-DB geführt, wie kann nun eine Überweisung in der Konten-DB und der Audit-DB erstellt werden, ohne Inkonsistenz hervorzurufen?


Wenn nun **zwei Transaktionen** verwendet werden, existiert wieder ein Problem, dass die erste Transaktion gelingen kann und die zweite nicht.

=> **Transaktionsmanager**

>[!Info]
>Mit einem Transaktionsmanager können verschiedene Transaktionen zusammengeführt werden.

Die Beiden Systeme müssen aber über einen kompatible Transaktionsmechanismus verfügen.
![[verteilte Transaktion.png]]
```java
void auditedTransferAmount(Account from, Account to, int amount) {
	try {
		// Beginne verteilte Transaktion TV
		TransactionManager.beginTransaction(); 
	
		// lokale Transaktion
		transferAmount(from, to, amount); 
		audit(Action.TRANSFER, getUser(), from, to, amount); 

		// Kommit
		TransactionManager.commit();
	} catch (Throwable t) {
		TransactionManager.rollback(); 
		throw t;
	}
}
```


## Two-Phase-Commit
Der Two-Phase-Commit ist der Standard-Algorithmus für verteilte Transaktionen.
- Koordination von einem Teilnehmer der verteilten Transaktion. z.B. der ersten Transaktion, welche ein Commit ausführt.
- **Phase 1**: Koordinator fragt alle beteiligten Systeme, ob Sie die Transaktion erfolgreich abschliessen können (YES) oder nicht (NO).
- **Phase 2:** Koordinator trifft entscheidung. Entwer alle comitten (nur YES) oder all brechen die Transaktion ab (mindestens ein NO erhalten)
![[TwoPhaseCommit.png]]

**Im Detail**:
**Voting**
- Koordinator sendet `PREPARE`-Anfrage
- Teilnehmer antworten mit `YES` falls die Transaktion ausgeführt werden kann, ansonsten mit `NO`
**Decision Phase**
- Koordinator sammelt alle Antworten.
	- Koordinator trifft Entscheidung. Entweder alle comitten (nur YES) oder all brechen die Transaktion ab (mindestens ein NO erhalten)
- Jeder Teilnehmer wartet auf die Antwort des Koordinators.
	- Bei `COMMIT` wird die Transaktion ausgeführt.
	- Bei `ABORT` führt er ein Rollback durch.
- Falls ein Koordinator crashed, können andere Teilnehmer angefragt werden.