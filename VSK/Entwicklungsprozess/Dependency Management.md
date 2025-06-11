>[!Definition]
>Das Dependency-Management beschreibt die Organisation und die Technicken für den Umgang mit Abhängigkeiten zu anderen Modulen

- Häufig auch der Begriff **Package Management**

Abhängigkeiten können zu:
- internen Module (im selben Projekt)
- externen Modulen (anderes Projekt oder Organisation)
stammen.

Abhängigkeiten werden in binäre (kompilierter) Form aufgelöst. Diese werden in [[Binary-Repo]] verwaltetet und **Packagemanager-Tools** kommen zum Einsatz

**Beispiele**
- NuGet-> für .NET
- apt -> Advanced Packaging Tool: Debian
- Yum -> Yellowdog Updater -> Redhat
- P2 -> OSGi basiertes Komponentensystem
- npm -> Node Package Manager
- Gems -> Ruby

>[!Info]
>Zentrale Ablage auf einem Server, ein standardisiertes Format, zusätzliche Metainformationen, typische mit Abhängigkeiten versehen, Sicher der Konsisten (z.B. [[Hashfunktionen]]) geregelte Zugriffsprotokolle, Suchmöglichekeiten, etc.

## Java
- Binäre Module werden bei Java typisch als JAR-Datein ausgetauscht.
- Java umfasst seit Version 9 Mechanismen zur Modularisierung und Definition von Abhängigkeiten, umfasst aber nicht die Versionierung und die Ablage.
- Ursprünglich wurden von Hand JARs ins `/lib` verzeichnis kopiert und dem Classpath hinzugefüt.
	- Fehleranfällig
	- JAR-Hell bei vielen Dateien und [[Transitive Dependency|transitiven Abhängigkeiten]].

