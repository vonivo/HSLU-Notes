---
aliases:
  - Betriebssystem
---
# Generell
Betriebssysteme (OS → Operating System) sind hardwarenahe Software.

Softwareschicht zwischen Anwendung und Hardware:
- Verwalten von Hardwarekomponenten
- Einfache und komfortablere Schnittstellen für Anwendungen
- Erweiterte/[[Virtuelle Maschine (Betriebssystem)|Virtuelle Maschine]] → mächtiger als die eigentlich durch Hardware realisierte Maschine

![[Betriebssysteme.png]]

Das Betriebssystem verwaltet Ressourcen:
- [[Interprocess Communication|Prozessmanagement]]
- [[Memory Management]]
- [[Gerätemanagement]]

Die Zuteilung von Ressourcen nennt man **Multiplexing** 
- zeitlich (für [[Prozessor|CPU]], Schnittstellen, Drucker): Prioritäten udn Fairness
- räumlich (Festplatte, RAM): Effizienz, Zugriffsschutz

Das Betriebssystem macht auch Benutzer/Rechteverwaltung

Das OS läuft im [[Kernel Mode]]
Applikationen laufen im [[User Mode]]
Mithilfe von OS Aufrufen welche Software [[Interrupts]] (Trap) verwenden kann zwischen den beiden Modi umgeschaltet werden. 

Für Konkrete Informationen über einzelne Betriebssysteme sieh [[Konkrete Betriebssysteme]]