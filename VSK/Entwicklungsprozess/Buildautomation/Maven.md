Apache Maven ist ein [[Build-Werkzeug]] welches in Java implementiert ist und im Java-Ökosystem oft genutzt wird.

Maven hat einen **deklarativen** Ansatz in `XML`. Das zentrale Objekt ist das `pom.xml`-File (Project Object Model).

Maven definiert alle Metainformationen, Plugins und Dependencies.

- Da Maven populär ist, existiert praktisch für jede IDE eine Integration.
- Maven benötigt nur die JDK.
- Basiert auf einem **globalen, binären** Repository.

## Konzept
Maven ist sehr minimal und kann alleine wenig. Es definiert im Wesentlichen die **POM**-Struktur und die **Lifecycle-Phasen**.

Alles andere wird über dynamisch ladbare **Plugins** (unabhängige Releases) erledigt.
Dadurch wird Maven extrem flexibel und beliebig erweiterbar.

Ein Nachteil:
- Neben den von Maven selbst entwickelten **Core-Plugins** existieren viele **Dritt-Plugins**. Bei diesen Dritt-Plugins kann sich die Qualität extrem unterscheiden.

### Lifecycle
Der von Maven definierte Lifecycle ist in folgende Phasen aufgebaut und ist aufbauen gestaltet:
1. **validate**: Validiert Projektdefinition
2. **compile**: Kompilation der Quellen
3. **test**: Ausführen der Unit-Tests
4. **package**: Paketieren der Distribution (JAR ,EAR, WAR etc.)
5. **verify**: Ausführen der Integrations-Tests
6. **install**: Deployment in lokales `.m2`-Repo
7. **deploy**: Deployment in zentrales Repository

=> Aktivierte Plugins binden sich meistens selbständig in eine Lifecycle-Phase ein.

## Depency-Management
Maven integriert auch ein [[Dependency Management]].
Abhängigkeiten werden im POM deklariert, sowohl von Plugins als auch Libraries und werden aus einem Zentralen Repository geladen.

Alle heruntergeladenen Artefakte werden in einem lokalen Repository (`$HOME/.m2`-Verzeichnis) gecached.
Das `.m2` ist hierarchisch nach der Maven-Koordinaten aufgebaut.
Firmen können auch eingene Repositories verwenden.

Maven selbst erlaubt eine Modularisierung des eigenen Codes.