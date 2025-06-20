Das Deployment von Software umschliesst folgende Teilbereiche:
- **Verteilung**: Verteilung der Software über Downloads / Datenträger oder SMS (Software Management System) oder z.B. OpenWebStart, inklusive Dokumentation.
- **Installation**: Kopieren der nötigen Dateien an die vorgesehenen Orte und Registrieren der Anwendung, allenfalls Überprüfung, ob das Zielsystem für die Anwendung geeignet ist.
- **Konfiguration**: Einstellungen der Anwendung auf Benutzer, Netzwerkumgebung, Hardware etc.
- **Organisation**: Planung, ggf. Produktion, Information (Marketing), Schulung, Support

## Zeitpunkt
Deployment findet am Ende des Projekts statt.
Aufgrund iterativer und agiler Entwicklung soll das Deployment [[Continious Integration|kontinuierlich]] stattfinden.

Es sollen Einzelne Build-/Sprint-/Iterationsergebnisse fortlaufend z.B. auf interne Testumgebungen Deployed werden.

**Continious Delivery** als Grundlage für Conitnious Deployment. Das Deployment kann Staging-Umgebungen (DEV, TEST, etc.) gemacht werden.

## Umfang
Technische Aspekte des Deployments:
- [[Deployment Diagramm]]
- Installations- und Deinstallationsprogramme
- Konfiguration
- Installationsmedium
- Repositories

**Organisatorische Aspkete**
- [[Softwarekonfigurationsmanagement|Konfigurationsmanagement]]: Welche [[Komponente|Komponenten]] bilden welchen Release oder [[Bill of Material]].
- Installations- und Bedienungsanleitungen
- Erwartungsmanagement: Welche Funktionalität ist vorhanden.
- Bereitstellung von Support

**Deployment-Doku** als Informationsquelle


## Open Source Projekte
In einem OSS-Projekt wird eine Software meisten auf zwei Arten deployed:
1. **Binär**: Enthält binäre Runtime plus Dokumentation. Häuffig als `*.zip`-Datei.
2. **Source**: Enthält nur den Quellcode und alle notwendigen Buildartefakte. Häuffig über [[Versionskontrollsysteme|VCS]]-Zugriff.


