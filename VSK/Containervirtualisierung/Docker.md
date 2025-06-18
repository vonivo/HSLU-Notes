>[!Definition]
>Docker ist eine leichtgewichtige Virtualisierungsart die vollständig isoliert, aber trotzdem direkt auf dem Host ausgeführt wird. Docker ist dadruch sehr schlank und schnell. (siehe [[Container]])

Mit Docker kann eine lauffähige Applikation **inklusive ihrer Laufzeitumgebung** in einer standardisierten Form verteilt werden und ermöglicht dadurch eine unkomplizierte Installation.

**Wichtige Begriffe**
- **Container**: Konkrete Laufzeitumgebung (Instanz) eines Images
- **Image**: Vorlage für eine Laufzeitumgebung. Wird dieses gestartet, entsteht ein Container. Enthält die im Container ausführbare Anwendung in Form eines virtuellen, geschichteten Dateisystem.
- **Tag**: Versionslabels für Images (nicht immutable)
- **Volumes**: Virtueller Speicher, dass Daten persistent bleiben.
- **Netzwerk**: Nötig, damit Docker untereinander oder mit dem Host kommunizieren können.
- **Registry**: Ort an dem mehrer Docker-Repositories verfügbar sind. (z.B. Dockerhub)
- **Repository**: Strukturierter, versionierter Ablage Ort für ein Docker-Image

**Funktionsweise**
- Verwendet Techniken vom Linux-Kernel (cgroups, namespaches und root-jail) um Isolation zu erreichen.
- Basistechniken werden später von Docker.io in einer Schnittstelle libcontainer zusammengefasst.
- Kann problemlos in einer virtuellen Maschine laufen. (z.B. auf WSL)

**Konzepte**
- Docker ist ein typisches CLI-Tool
- Alles in Docker bekommt einen eindeutigen ID welche auf einem Hash basiert.
- Von der ID muss nur so viel spezifiziert werden, dass diese auch eindeutig ist.

>[!Info]
>Docker ist nur mit WSL 2 kompatibel.



## Einsatz
1. Spontanes, einfaches ausprobieren von (Server-)Anwendungen.
	- Ohne zusätzliche Installation einfach OOTB.
2. Nutzung als Buildumgebung für unterschiedliche, fremde, auf dem Host nicht installierte Plattform.
	- Kann auch für eine gesamte Entwicklungsumgebung genutzt werden, **DEV-Containers**
3. Deployment und Betrieb einer produktiven Anwendungen.
	- Komplet konfiguriert und lauffähiges Image.
	- Verteilung und Archivierung der Images in Registries/Repositories.
4. Schnelle flexible Testumgebung.
	- Integration in eigene Testfälle möglich (Testcontainer)


## Tools
- `ctop`: Shell für die permanente Anzeige aller Container
- `dive`: Shell-Tool für die Analyse von Images (praktisch für Fehlersuche)
- `layzdocker`: Shell-Tools als Ersatz für Docker-Desktop
- `better-docker-ps`: Vermeidet Zeilenumbrüche bei `docker ps`
