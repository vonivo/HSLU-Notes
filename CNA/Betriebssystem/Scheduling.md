---
aliases:
  - Scheduler
---
Als Scheduling bezeichnet man die Art und Weise wie ein [[Betriebssysteme|Betriebssystem]] die Abbarbeitung seiner [[CNA/Betriebssystem/Prozesse]] plant. Je nach [[Betriebsmodi]] gibt es unterschiedliche Anforderungen an das Scheduling. 
Dafür wird ein **Scheduler** verwendet. 
→ Dieser entscheidet welcher Prozess als nächstes ausgeführt wird ([[CNA/Betriebssystem/Prozesse#Prozesszustände|Running]])

# Scheduling [[Algorithmus|Algorithmen]]
Scheduling [[Algorithmus|Algorithmen]] können unterschieden werden in:
- **Preemptive Scheduling**
	- Ein Prozess rechnet so lange bis er blockiert oder selbst die [[Prozessor|CPU]] freigibt
- **Nonpreemptive Scheduling**
	- Der Scheduler **suspendiert** einen Prozess nach einer bestimmten Zeit

## Beispiele
- **SFJ = Shortest Job First** → Nonpreemptive, geeignet für Batch Jobs
	- Kürzere [[CNA/Betriebssystem/Prozesse]] werden bevorzugt, dadurch sinkt die durchschnittliche Laufzeit
- **Shortest Remaining Time** → Preemptive, geeignet für Batch Jobs
	- Prozess mit der wenigsten verbleibenden Zeit wird bevorzugt
- **FCFS** = First Come First Served → Nonpreemptive, geeignet für Batch Jobs
	- [[Prozessor|CPU]] wird in der Reihenfolge assigned wie sie angefragt wird
- **Round Robin**  → Nonpreemptive, geeignet für Interaktive Systeme
	- Jeder Prozess bekommt einen Zeitintervall, wenn diese vorüber ist wird der Prozess suspendiert und der nächste kommt dran (sehr fair)
- **Prioritäten Scheduling** → Geeignet für interaktive System
	- Jeder Prozess bekommt eine Priorität, je höher die Prio desto früher wird er ausgeführt. Damit [[CNA/Betriebssystem/Prozesse]] nicht ewig warten müssen wird ihre Prioriät stetig erhöht
- **Earliest Due Date** → Geeignet für Realtime Systeme
- **Gemischte Verfahren** kommen auch zum Einsatz:
	- Beispiel: Grundsätzlich Priority, haben mehrere Prozesse die gleiche Prio dann Round Robin
	- Aufwändig bei Multicoresystemen