Die Verteilung einzelner `*.class` Dateien ist in Java in der Regel nicht Machbar.
Daher existiert das Basiskonzept, dass man mehrere `*.class` Datein und Ressourcen in ein unkomprimiertem Zip-Foramt zusammenfasst.
- **J**ava **AR**chive ([[JAR]])
- **J**ava **MO**dule (JMod)

Oder erweiterte Container:
-  **W**eb **AR**chive (WAR mit `META-INF/web.xml`)
- **E**nterprise **AR**chive (EAR, Mit `META-INF/application.xml`)

## Applikation für Endbenutzer
Für Endbenutzer werden Applikationen oft mit einem automatisierten Installationsprogramm (`setup.exe`) und Anleitung, ggf. sogalr inkl JRE ausgeliefert.

Dabei kann auf ein **Single**-**[[JAR]]** oder ein **FAT-[[JAR]]** gesetzt werden.

## Serverapplikation
Meist separierte [[JAR]]-Datein für gezielte Update.
Bei Microservices meist ein Single-[[JAR]] oder als [[VSK/Containervirtualisierung/Docker|Docker]]

## Library/Komponente
Typisch als Download verfügbar in einem [[Binary-Repo]]
- mit konsistenter Versionssemantik.
- Inklusive Metadaten in strukturierter Form für automatisches [[Dependency Management]]
