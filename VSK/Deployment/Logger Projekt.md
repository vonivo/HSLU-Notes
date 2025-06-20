# Variante 1
Start der Applikation mit Classpath welcher alle notwendigen [[JAR]]-Dateine enthält
1. Argumente -cp beim Start (z.B. über Shellskript)
	- Einfache Erweiterung des Classpaths.
	- Eifnacher Austausch einzener JARs
2. Class-Path Eintrag in `META-INF/MANIFEST.MF` in der JAR-Datei der Anwendung
	- JAR (Manifest) muss bei Änderungen neu gebaut werden.

**Depencies auflösen**
```sh
mvn dependency:list –DincludeScope=compile
```

**Dependencies kopieren**
```sh
mvn dependency:copy-dependencies -DincludeScope=compile
```
Resultate liegen danach in `.target/dependency`



## Variante 2
FAT-Jar, welche alle Klassen enthält.

 Muss immer komplett neu gebaut werden.


## Aplikation starten
**Maven**
```
mvn exec:java –D"exec.mainClass=ch.hslu.vsk.demoapp.DemoApp"
```


**Direkt als JAR**
```sh
java -cp "./g01-demoapp-1.0.0.jar;./dependency/*"
	ch.hslu.vsk.demoapp.DemoApp
```
Voraussetzung: Dependecies wurde allen ins `./dependency` kopiert.



## Container
**Vorteile**
- Bau des Images und Start-Befehl sehr einfach
- Simples Dockerfile zur Konfiguration
- FAT-JAR kann auch ausserhalb des Containers einfach genutzt werden.

**Nachteile**
- FAT-JAR relativ gross.
- Fette Layer
- Problematik mi den Manifesten und Konfigurationen.

### Layerd Image
**Vorteile**
- Feingranulare Trennung der Applikation, Dependecies und Konfiguration in separaten Layers
- Unterschiedliche Änderungshäuffigkeit berücksichtigt.
- Autmoatisierung durch [[Docker im Java Umfeld#Google Jib Docker Plugin|JIB]]

**Nachteil**
- Bau des Images komplizierter.
- Komplexeres Dockerfile
- Applikation nur im Container lauffähig.