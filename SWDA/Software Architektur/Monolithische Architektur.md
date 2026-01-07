## Monolithisches Design
- Ein **nicht modularisiertes**, monolithisches Design (auf Klassenebene) ist tatsächlich sehr schlecht!
- Die Codebasis besitzt fast keine Struktur und Design -> vergleichbar mit Spaghetti-Code
- **Problem:** Gut strukturierter und modularisierter Code errodiert mit der Zeit -> **hohe Disziplin wichtig.**

## Monolithisches Deployment
- Sauber modularisierte und strukturierte Applikation.
- Durch das monolithische Deployment (alles wird auf einmal deployed) wird das Deployment sehr einfach.
	- Eine Mobile-App, welche intern z.B. aus zehn verschiedenen Komponenten besteht, kann problemlos als «monolithisches» Packet (am Stück) verteilt werden.
	- Selbst eine grössere, umfangreichere (Web-)Applikation, welche ebenfalls streng modularisiert ist, kann letztlich relativ einfach als eine einzig.

**Nachteile**
- Die Grösse einer Deployment-Unit ist ein entscheidender Faktor
- Klumpenrisiko beim Deployment
- Der durch die Komponentenorientierung parallelisierte und entkoppelte Entwicklungsprozess, wird am Ende durch das «Nadelöhr» des Deployments wieder synchronisiert.

=> Lösung: Man beginnt die Applikation zu verteilen [[Verteilte Applikation]]
