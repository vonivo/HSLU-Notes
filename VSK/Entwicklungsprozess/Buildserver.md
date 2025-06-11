>[!Definition]
>Ein **Buildserver** ist eine Serversoftware, welche einen bereits [[Buildautomation|automatisierten]] Build eines Softwareprojekts ausführt, und die Resultate allen Entwickler im Team zur Verfügung stellt.

Der Build kann auf verschiedene Arten getriggert werden:
- Automatisch durch Änderung im [[Versionskontrollsysteme]].
- Automatisch durch Zeitsteuerung.
- Manuell durch Anwender.

**Vorteile**
- Entlastung von Entwickler von repetitiven Aufgaben.
- Häufigere Verifikation ([[Buildprozess]], Testing, Deployment etc.)
- Statistische Informationen über Entwicklungsprozess.
- Offensive (automatische) Informationen über den Zustand der Projekte.

**Beispiele**
- Jenkins
- GitLab
- TeamCitity
- GitHub

## Konfiguration
Es gibt zwei Ansätze für die Konfiguration einer Build-Piepline:
- Konfiguration ist vom Projekt vollständig getrennt.
	- Wird interaktiv auf dem Buildserver vorgenommen.
	- Infrastruktur wird vor Entwickler "geschützt"
	  -> Gewaltentrennung
- Konfiguration ist im Repository:
	- Eher für Cloud-Hosting
	- Konfiguration direkt durch Entwickler
	- Weniger restriktiv, sehr häufig mit [[Docker]]
		-> Mehr Freiheit und Eigenverantwortung

Variante 1 eher bei Organisationen und Variante 2 eher bei OSS.


## Einsatz
Der Einsatz von Buildserver setzt andere Technologien voraus:
- [[Buildautomation]] mit [[Build-Werkzeug]]
- [[Versionskontrollsysteme]]

Es sollte eine **saubere Trennung** zwischen den Technologien bestehen:
- **Wann** wird dien Build ausgeführt: Buildserver / Anwender
- **Was** wird gebaut: [[Versionskontrollsysteme]]
- **Wie** wird geaut: [[Buildautomation]]
- **Wohin** gehen die Artefakte: Buildserver [[Binary-Repo]]

>[!error]
>Speziell das "**WIE**" sollte nie im Buildserver umgesetzt sein, sonder immer durch [[Buildautomation]] abgedeckt werden.


## Buildszenarien
- **Continious Builds**: Automatisch bei einer Änderung (Push/Merge Request / Pull-Request) im Versionskontrollsystem:
	- schnelle, möglichst kurze Builds
	- => Schnelles Feedback
- **Nightly**: Autmatisch nach Zeitsteuerung, typisch Nachts.
	- Eher umfangreiche Builds.
	- Auch für zeitintensive Tests und Metriken.
	- => Am Morgen stehen umfassende Resultate zur Verfügung.
- **Release**: Manuell Ausgelöst
	- Build einer auslieferbaren Version, im VCS getaggged.
	- => Reproduzierbarkeit gewährleisten.

## Integration
Moderne Buildserver sind extrem gut in IDEs integrierbar und bieten selber gute Integration für:
- verschiedene Tools
- [[Versionskontrollsysteme]]
- Kommunikationstechnologien
- verschiednen Visualisierungen / Plugins

Meistens lassen sie sich auch mit:
- Issue-Tracking
- Code-Review Werkzeugen
- etc.
verknüpfen.