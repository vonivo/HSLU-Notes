Ein gegenseitiger Ausschluss muss vier Bedingugnen erfüllen:
1. In einem **kritischen** Abschnitt darf sich zu jedem Zeitpunkt höchstens **ein Thread** aufhalten. (Schutz vor [[Race Condition|Race Conditions]])
2. Es dürfen **keine Annahmen** über die zugrundeliegende Hardware gemacht werden.
3. Ein Thread dar **andere Threads nicht blockieren**, ausser in einem kritischen Bereich.
4. Es muss sichergestellt sein, dass ein [[Thread]] **nicht unnendlich lange warten** muss, bis er in einen kritischen Bereich eintreten kann.

## Monitorkenept
Ein Monitor ist ein programmiersprachliches Konzept zur Synchronisation von Zugriffen (quasi)parallel laufender Prozesse oder Threads auf gemeinsame Ressourcen.

- In Java 1.0 wurde das Monitorkonzept [[Synchronized]] implementiert.
- Ab Java 1.5 wurde das [[Semaphore]]-Konzept eingeführt.

### Reentrant Monitor
Betritt ein Thread eine synchronisierte Methode/Abschnitt, dessen Lock er schon besitzt, kann er sofort eintreten ohne den lock-pool zu durchlaufen.

- Ohne diese Möglichkeit gäbe es keine Rekursion.
- Reduziert Parallelität.
- Kann geschwindigkeitssteigernd sein.

### Nested Monitore
- Ein Thread kann beliebig viele verschiedene Locks ergreifen.
- Geschachtelte Monitore führen leicht zu [[Deadlock|Deadlocks]]