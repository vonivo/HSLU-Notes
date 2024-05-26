Eine faire Zeitmessung für einen [[Algorithmus]] zu erstellen ist nicht ein Triviales unterfangen. Da viele Einflussfaktoren die Messung verfälschen können.

## Einflussfaktoren
- Auswahl der Daten und Datenmenge
- Quelle der Zeitmessung und deren Genauigkeit
- Belastung des Prozessors
- "Kaltstart" einer Java-Anwendung (Classloading)
- Verzögerung durch den JIT (Just-In-Time-Compiler)

## Möglichkeiten für Zeitmessung
**System.currentTimeMillis()**
Liefert die **absolute** Anzahl Millisekunden seit dem 1. Januar 1970 aus der Rechenzeit (VM-Übergreifend). Beste erreichte Genauigkeit liegt bei **1 Millisekunde**

**System.nanoTime()**
Liefert **innerhalb** einer VM eine **relative**, fortlaufende Zeit in Nanosekunden.
Beste Genauigkeit liegt bei **1 Nanosekunde**


## Regeln für die Zeitmessung
- Granularität einer Messung sollte deutlich kleiner sein als die erwartete Zeitdauer.
	**System.currentTimeMillis()** eignet sich daher nicht für Messungen, welche wenige Millisekunden dauern. (Messung kann z.B. übermehrere Iterationenn gemessen werden und danndividiert.)
> [!warning]
> Mehrere Iteration können Resultat massiv abändern, wegen dem JIT oder Nachladen von Klassen
- Messungen mehrfach wiederholen.
	Empfehlung: **Mindestens 3 mal**.
	Es kann jederzeit unerwartete Ausreißer geben.
- Erste Messung immer verwerfen.
	Beim ersten Start der Messung ist nichts optimiert, Speicher muss alloziert werden, Klassen geladen, usw. 
- Nebenlast des Prozessors möglichst gering halten.
- Testdaten wohlüberlegt bestimmen