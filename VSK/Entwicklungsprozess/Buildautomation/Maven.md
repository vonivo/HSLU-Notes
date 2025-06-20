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
4. **package**: Paketieren der Distribution ([[JAR]] ,EAR, WAR etc.)
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

- Maven selbst erlaubt eine Modularisierung des eigenen Codes.
- Maven erlaubt die Auflösung von [[Transitive Dependency|transitiven Dependencies]] und kann auch Versionskonflikte beheben.
- Erkennt Zyklische Dependencies
- Maven erlabut auch das Auswerten von Dependencies als Graph [[Graphenalgorithmen]]



### Maven Koordinaten
Ein Maven Projekt wird über 3-Punkte global eindeutig identifiziert:
1. **Group-ID**: Meistens "reverse doamin name" der Organisation und einen Zusatz für eine Projektgruppe `ch.hslu` + `vsk`
2. **ArtifactId**: Entspricht häuffig dem Namen des Projekts. `stringpersistor-api`.
3. **Version**: Empehlung: [[Semantic Versioning]]

**Im POM**
```xml
<groupId>ch.hslu.vsk</groupId>
<artifactId>stringpersistor-api</artifactId>
<version>8.0.3</version>
```

**Kurzform**
```
org.slf4j:slf4j-api:2.1.0
```

### Deklaration im POM
Benötigte Dependencies werden als Kind des Tags `<dependencies>` angegeben:

```xml
<dependencies>
...
	<dependency>
		<groupId>ch.hslu.vsk</groupId>
		<artifactId>stringpersistor-api</artifactId>
		<version>8.0.3</version>
		<scope>compile</scope>
	</dependency>
...
</dependencies>
```
- Beim Build werden diese Dependencies nun automatisch heruntergeladen und ins lokale `.m2`-Repo gespeichert.
- Der Build referenziert diese JARs dann über den Class-Path

#### Scopes
Da beim Testen oft spezielle Dependenies verwendet, welche man im Produktions-Code nicht haben möchte kennt Maven Scopes.
Diese Scopes definieren den Gültigkeitsbereich einer Dependency.

**geläuffigste Scopes**
- **compile** -> Dependency wird für die Kompilation und zur Laufzeit des Programms benögitg (Default)
- **test** -> Dependecy ausschliesslich für die Kompilation und Ausführung der Testfälle.
- **runtime**: Dependency nur für Laufzeit, aber nicht für Kompilation (dynamisch geladenen Implementationen)

Aus den Scopes werden spezifische Classpaths gebaut -> implizite Verifikation des Design.

#### Multimodule Projekt
Damit die verschiedenen Versionen von Dependencies in einem Multi-Modul-Projekt zentral an einem Ort definiert werden können existiert der Tag `<dependencyManagemnt>`. Dieser Tag ist im Parent-POM zu finden und erstellt eine Base-Line mit allen Dependencies und deren Versionen.

Im Sub-Moudl muss dann nur noch die GroupId und und die ArtifactId spezifiziert werden:

**Parent pom.xml**
```xml
<dependencyManagement>
	<dependencies>
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-api</artifactId>
			<version>2.1.0</version>
			<scope>compile</scope>
		</dependency>
	</dependencies>
...
</dependencyManagement>
```

**Child pom.xml**
```xml
<dependencies>
	<dependency>
		<groupId>org.slf4j</groupId>
		<artifactId>slf4j-api</artifactId>
	</dependency>
</dependencies>
```

Alternative Technickt [[Bill of Material]]
### Quell-Repos definieren
Wenn ein eigenes [[Binary-Repo]] verwendet wird, kann dies wie folgt definiert werden:
```
<repositories>
	<repository>
		<id>gitlab-maven-repo-vsk-stringpersistor-api</id>
		<url>https://gitlab.com/api/…/…/packages/maven</url>
	</repository>
</repositories>
```

### SNAPSHOT-Version
Druch die Versionierung kann Maven:
- neuen Versionen erkennen.
- Automatische Verwendung des neusten Bugfixes.
- Angabe von Versionbreich welche Kompatibel sind etc.

Da [[Binary-Repo|binäre Repos]] es nicht erlauben bestehende Versionen zu bearbeiten, müsste in der Entwicklung für jede "Entwicklungs-Version" eine neue Version erstellt werden.

Um dies zu verhindern, existieren die SNAPSHOT-Versionen. Snapshot versionen sind "unstable-Versionen" "überschrieben werden können".

Um eine Snapshot-Version zu erstellen wird `-SNAPSHOT` der Version angehängt.

