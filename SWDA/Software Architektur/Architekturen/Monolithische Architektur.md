>[!Definition]
>Ein Monolith ist eine Single-[[Tier|Tiered]] Applikation. Alle Komponenten werden zusammen paketiert.
>Ein Monotlith ist dabei meistens unabhängig von anderen Applikationen.


## Monolithisches Design
- Ein **nicht modularisiertes**, monolithisches Design (auf Klassenebene) ist tatsächlich sehr schlecht!
- Die Codebasis besitzt fast keine Struktur und Design -> vergleichbar mit Spaghetti-Code
- **Problem:** Gut strukturierter und modularisierter Code errodiert mit der Zeit -> **hohe Disziplin wichtig.**

## Monolithisches Deployment
- Sauber modularisierte und strukturierte Applikation.
- Durch das monolithische Deployment (alles wird auf einmal deployed) wird das Deployment sehr einfach.
	- Eine Mobile-App, welche intern z.B. aus zehn verschiedenen Komponenten besteht, kann problemlos als «monolithisches» Packet (am Stück) verteilt werden.
	- Selbst eine grössere, umfangreichere (Web-)Applikation, welche ebenfalls streng modularisiert ist, kann letztlich relativ einfach als eine einzig.

**Vorteile**
- Einfaches Deployment
- Einfacher Betrieb
- Nur eine Code-Base
- Corss-Cutting-Concerns sind einfach adressierbar
- Gute Performance

**Nachteile**
- Die Grösse einer Deployment-Unit ist ein entscheidender Faktor
- Klumpenrisiko beim Deployment
- Der durch die Komponentenorientierung parallelisierte und entkoppelte Entwicklungsprozess, wird am Ende durch das «Nadelöhr» des Deployments wieder synchronisiert.
- Gewisser Verlust der Agilität.
- Ein Monolith skaliert weder horizontal noch vertikal wirklich gut.
- Ein Monolith ist nicht so fehlertolerant, da ein Fehler die ganze Applikation blockieren kann.
- Ein Monolith ist an eine bestimmte Technologie gekoppelt.

=> Lösung: Man beginnt die Applikation zu verteilen [[Verteilte Applikation]]
