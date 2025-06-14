[[Docker]]-Images werden in Layers erstellt. Jeder Layer ergänzt Dateien oder führt ein Befehl aus.  Images basieren selbst typischerweise auf existierenden Images.

Die einzelnen Schritte für die Erstellung eines Docker-Images werden in einem **Dockerfile** beschrieben (Textdatei mit dem Namen `Dockerfile`)
- Dadurch wird der Erstellungsprozess Reproduzierbar.
- Dockerfile wird versioniert via VCS.

**Beispiel**
**Image**
```Dockerfile
FROM amazoncorretto:21.0.6-alpine
COPY target/oop_maven_template.jar /opt/demo/oop_maven_template.jar
CMD ["java","-jar","/opt/demo/oop_maven_template.jar"]
```
- **FROM**: Das image Basiert auf `amazoncorretto:21.0.6-alpine`
- **COPY**: Aus dem Targetfolder wird das JAR-File ins `opt/demo/` Verzeichnis kopiert.
- **CMD** Der Startbefehl des Images für `docker run` wird hinterlegt.

**Build**
```sh
docker build . -t "vonivo/vsk-demo:latest"
```
Das Image steht danach in der lokalen Registry zur Verfügung:
- `vonivo` Namespace des Images
- `vsk-demo`: Name des Images
- `latest` Neuste Version,

**Push**
```
docker push <user>/oop-demo:latest
```
Mit diesem Befehl wird das Image in eine Docker-Registry gepushed.

## Herausforderungen
- Images sollten entsprechend der jeweiligen Plattfrom und Distribution konfiguriert werden (viel Knowhow des Zielsystems nötig)
- Darauf achten sinnvolle Layers zu builden.
	- So wenige wie möglich, so viele wie nötig
	- Möglichst ähnliche Änderungshäuffigkeit pro Layer
	- Möglichst kompakte Images.

Beim Build des Images werden die Dateiinhalte und Kommandos gehashed. Ein Layer wird nur neu erstellt, wenn sich der Hash ändert.
