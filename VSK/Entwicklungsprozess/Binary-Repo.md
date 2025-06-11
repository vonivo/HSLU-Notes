Es gibt verschieden Binary-Repos für [[Maven]].
- Maven Central https://search.maven.org/ (Orginal)
- Maven Central https://central.sonatype.com/ neues UI
- Google Maven Repo https://maven.google.com/

Schreibrechte auf diesen öffentlichen Repos bestehen in der Regel keine Schreibrechte und nur ausgewählte Pakete werden aufgenommen.
- Daher werden oft interne Repos zusätzlich verwendet.

**Beispiele**
- JFrog/Artifactory
- Sonatype/Nexus
- Apache Archiva

## Dependecy Management mit Maven Repositores
Es muss zwischen der **Format** der zentralen Ablage und dem **Werkzeug** unterschieden werden.

Beispielweise können mit [[Build-Werkzeug|Gradle]] ebenfalls Dependencies aus dem Maven-Repo geladen werden.

=> Das Format des Repositories ist zum Quasi-Standard geworden.

## Deployment
- Deployment meistens als JAR.
- Um Stabilität von Builds zu gewährleisten, dürfen für gewöhnlich keine Versionen gelöschen werden.
- Auch manuelles Deployen ist meisten nicht erlaubt, sonder es wird **nur durch einen automatischen verifizierbaren Release-Prozess** welcher von einem [[Buildserver]] ausgeführt wird, deployed.