Java-Applikationen können sehr unterschiedlich Deployed werden:
- **Single-[[JAR]]** -> Alle [[Dependency Management|Abhängigkeiten]] in einem [[JAR]].
- **App-[[JAR]] und Dependey-[[JAR]]** -> `classpath` notwendig, typisch über ein Startscript.
- Alles in einem, oder in getrennten Layers?
- Modularisierte Applikation JPMS (Java Platform Module System)

## Fabric8 [[Maven]] Docker Image Plugin
- Setzt ein Docker-Image voraus.
- Konfiguration teilweise über das Maven POM
	- Minimal, z.B. für lokalen Start über Maven

## Google Jib [[Docker]] Plugin
- Sehr hohe Automatisation
- Konfiguration ausschliesslich über POM.
- Image-Build und Deploy **auch ohne** Docker-Runtime möglich.