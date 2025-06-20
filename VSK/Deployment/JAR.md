Ein JAR beinhaltet eine vollständige Applikation und kann:
- Selber aus $1\dots n$ einzelenen JARs bestehen.
- Zusätzlich $0\dots n$ Dependecy JARs benötigen.

JARs können extern (Name) oder intern (Manifest) versiniert sein.
- Ab $>1$ JAR-Dateien ist ein Classpath notwendig.

## Single-JAR
Einzelne Komponenten/Libraries z.B. für Bugfixing leicht austauschbar, benötigt aber einen Dynamik des Classpaths.

## FAT-Jar
Zusammenfassung des Inhalts mehrere JAR-Dateien in einem einzigen JAR zwecks einfacherem Deployment.

**Vorteile**
- Einfach

**Nachteile**
- Redundanzen der Dependecies
- Problematik der Neusignierung und META-INF
