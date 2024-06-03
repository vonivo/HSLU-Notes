Eine Java-Anwendung wird in einer Java Virtual Machine (JVM) ausgeführt.
Dabei entspricht die JVM einem [[Multicore CPU|Prozess]] des [[Betriebssystem]].

Sobald ein Java-Programm gestartet wird, erzeugt die JVM den Main Thread.
Wenn das Betriebssystem selbst [[Contextswitching#Multithreading|Multithreading]] unterstützt, kann die JVM Java-Threads auf sie Abbilden.

Die Zuordnung der OS-Threads auf die Hardware-Threads übernimmt der Scheduler des Betriebssystems

Der aktuelle Thread kann mittels `Thread.currentThreas()` aufgerufen werden.


## Beenden eines Threads
Ein Thread gilt als beendet wenn:
- Die `run` Methode ohne Fehler beendet wird.
- In der `run`Mehtode eine [[Exceptionhandling|Exception]] auftritt, welche die Methode beendet.
- Wenn `System.exit()` aufgerufen wird.
- Der Thread von aussen aktiv beendet wird.

Wird ein Thread beendet, stellen sich folgende Anforderungen an den Thread:
- Benutzte Objekte werde in einem konsistenten Zustand hinterlassen.
- Ressourcen werden freigegeben.
- [[AD/Nebenläufigkeit/Thread/Task]] wird zu Ende geführt.
- Kein neuer [[AD/Nebenläufigkeit/Thread/Task]] wird begonnen.

### Aktives Beenden
Ein Thread kann durch eine anderen Programmteil wie folgt beendigt werden:
- Erzwungen (forceful cancelation) -> sofortiger Abbruch.
- Verzögert (deferred cancelation) -> Abbruch beim nächsten Abbruchpunkt.
- Kooperativ (cooperative cancelation) -> Thread wird geben sich selbst durch ein `return` zu beenden.

Java verwendet das kooperative Beenden, erfordert mehr Programmieraufwand.

### Auf das Ende eines Threads warten
Über die `thread1.join()` kann der Aufrufende Thread angewiesen werden auf die Beendigung von `thread1` zu warten.

Der Aufruf vom `join()`ist dabei [[Blockierender Aufruf|blockierend]], ist `thread1` bereits terminiert kehrt die [[Methode]] direkt zurück.