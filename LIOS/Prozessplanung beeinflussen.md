Bei jedem Computer kommt es zu Szenarien, bei dem mehr Prozesse gleichzeitig bearbeitet werden sollten als möglich.

Dabei hat jeder Prozess ein anders Mass an Wichtigkeit. Diese wird über *Scheduling-Policies* in Verbindung mit der *Prozesspriorität* festgelegt.

Mögliche Scheduling-Policies:
- Prioritätscheduling -> Strikt nach Priorität abarbeiten
- Round-Robin

[[Linux]] verfügt über verschieden Policies die für die Verarbeitung
1. interaktiver Anwendungsanforderungen,
2. nicht interaktive Batch-Anwendungsverarbeitung (Non-Real-Time-Scheduling) und
3. Echtzeit-Anwendungsanforderungen (Real-Time-Scheduling)
konzipiert.


Aktuelle, (normale) Non-Real-Time-Scheduling-Policies verwenden den Completely Fair Scheduler (CFS), der statt
Prioritäten, Prozesse, die auf CPU-Zeit warten, in einer binären Suchstruktur organisiert.

- Diese Richtlinie ist am besten, wenn eine große Anzahl von Threads vorhanden ist oder wenn der Datendurchsatz Priorität hat, da sie eine effizientere Planung von Threads im Laufe der Zeit ermöglicht.
- Wenn diese Richtlinie verwendet wird, erstellt der Scheduler eine dynamische Prioritätsliste, die teilweise auf dem Niceness-Wert jedes Prozess-Threads basiert. Administratoren können den Niceness-Wert eines Prozesses ändern, aber nicht die dynamische Prioritätsliste des Schedulers direkt ändern.

# Nice-Wert, Real-Time-Prozessprio un ProzessPrio
Allen Prozessen wird ein Prioritätswert *PR* zugeordnet, damit alle Scheduling-Policies damit umgehen können.

Je nach dem werden nice-Werte oder Real-Time-Prozessprioritäten dazu gemappt.

-> Ein Nice wert von $-20$ wird der Priorität $0$ im Befehl `top` zugeordent. Ein nice-Wert von $19$ dementsprechend der Priorität $39$
-> Real-Time-Prioräten sind generell höher als die von Non-Real-Time-Prozessen

![[ProzessPriorisierung.png]]