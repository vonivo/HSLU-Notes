Popek und Goldberg haben 3 Anforderungen an ein physisches und virtuelles System gestellt:

- **Gleicheit**: Jedes Programm ausgeführt in einer virtuellen Maschine verhält sich genau so, wie wenn es auf der originalen Maschine ausgeführt wird.
- **Effektivität:** Wann immer möglich sollte die Instruktionen nicht auf dem virtuellen Prozessor, sondern direkt auf dem physischen Prozessor ausgeführt werden. (nur harmlose Instruktionen)
- **Ressourcenkontrolle** 
	- VMM hat die komplette Kontrolle über Ressourcen wie Memory I/O der Peripheriegeräte aber nicht unbedingt über Prozessaktivitäten
	- Es muss für jedes Programm unmöglich sein, die System Ressourcen zu beinflussen. Der Verteiler Allocator des Kontrollprogramms muss bei jedem dieser Versuche aufgerufen werden.

Was ist ein Hypervisor oder VMM (Virtual Machine Monitor)?
1. Stellt eine Umgebung zur Verfügung, welche identisch ist mit der Originalen Maschine (nur Teile davon)
2. Programme, die in dieser Umgebung laufen zeigen im schlechtesten Falle eines geringen Geschwindigkeitseinbusses.
3. Die VM ist die vom VMM erzeugte Umgebung.


Ein Hypervisor besteht aus folgenden 3 Elementen:
1. **Dispatcher**: seine Initial Insturction ist auf dem Speicherplatz, wohin die HW trapped.
2. **Allocator**: entscheidet, wer elche Systemressourcen bekommt. Er hat 1 oder n member.
3. **Interpreter** für alle Instruktionen, die trappen. Eine Interpreter Routine pro privilegierte Instruktion.

## Instruktionsklassifikation
Es existieren mindestens zwei Betriebsmodi:
- Uneingeschränkter Modus
- Eingeschränkter Modus

Instruktionen können in folgende Klassen unterteilt werden:
- **Privilegierte Instruktionen**: Trap, wenn Prozessor im Usermodus
	- **Kontrollkritische Instruktionen (control sensitive)**: Alle Instruktionen, die versuchen die Konfiguration von Systemressourcen zu verändern.
	- **Verhaltenskritische Instruktionen (instruction sensitive)** Alle Instruktionen, deren Verhalten oder Resultat abhängig vonder Konfiguration der Ressource (Inhalt der Relaction Register oder Prozessor modus ist.)
- **Harmlose Instruktionen**


## CPU Probleme
Je nach CPU-Architektur lösen nicht alle privilegierten Instruktionenen einen Trap aus.
Die x86 Architektur kenn 17 solcher Befehle, daher kann nicht einfach so eine VM erstellt werden.

## Arten von Hypervisors
Es gibt zwei Arten von Hypervisoren:
- Hypervisor ist direkt auf dr HW installiert und es gibt an sich kein OS, VMware ESXI, XEN, Hyper V
- Hypervisor wird auf dem Host OS installiert: bsp Virtualbox