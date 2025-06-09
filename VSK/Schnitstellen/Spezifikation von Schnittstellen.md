Zur [[Schnittstelle|Programmschnittstelle ]]gehört alles:
- was für die Benutzung der [[Komponente]] wichtig ist,
- was der Programmiere verstehen und beachten muss.

Jede Programmschnittstelle definiert eine Menge von Operationen mit folgenden Eigenschaften:
- Syntax
- Semantik
- Protokoll (synchron, asynchron)
- Nichtfunktionale Eigenschaften,
## Dokumentation
- **Syntax**: Notation analog zur verwendeten Programmiersprache
- **Semantik**: Präzise und kompakte textuelle Beschreibung, ggf. unter zu Hilfenahme formaler math. Konstrukte
	- Eingabeparameter: Welche Informationen werde an die [[Komponente]] weitergeleitet.
	- Ausgabeparameter: Welche Informationen kommen zurück
	- Zustandsänderungen der Komponente
	- Spezifikation, inwiefern sich Eingabeparameter auf die Zustandsänderung und die Ausgabeparameter auswirken.

## API
Eine API spezifiziert die Operationen sowie Ein- und Ausgaben einer Softwarekomponente.
Der Hauptzweck ist die Menge an Funktionen unabhängig von der Implementation zu definieren.