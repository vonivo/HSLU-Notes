Die grundlegende Idee ist, dass man die Services von [[Service Oriented Architektur|SOA]] nochmals kleiner schneidet.

Dabei wird die Domäne in **kleinere** voneinander **unabhängige** Teildomänen, die **bounded context** geteilt.

Die Granularität der Microservices nähert sich somit den grössen von [[SWDA/Software Architektur/Modularisierung|Modulen]].

Microservices sorgen aber dafür für eine **harte Modularität** durch Plattformgrenzen.

>[!Definition]
>Ein Microservices zeichnet sich wie foglt aus:
>1. Eine Applikation wird aufgeteilt in mehrere, kleine Services
>2. Jeder Service läuft in eigenem Prozess / auf eigener Plattform
>3. Leichtgewichtige Kommunikation (meist RESTfull/http/JSON)
>4. Voneinander unabhängig deploybar (und somit auch Releases)
>5. Automatisiertes Deployment (DevOps, PaaS, IaaS)


## 1. Eine Applikation wird aufgeteilt in mehrere, kleine Services 
Die Applikation wird primär vertikal in mehrere, möglichst unabhängige Teile aufteilt.
- Diese Teile sollten dabei möglichst autark arbeiten können und verfügen daher über ein eigene **Datenmodell** und **Businesslogik**.

Damit die einzelnen Datenmodelle identifiziert werden können, muss die Domäne in verschiedene **bounded contexts** aufgebrochen werden.
- Gutes Design -> Datenhaltung somit auch getrennt und gekapselt.
- Braucht Übung.

Einzelne Services sollten dabei möglichst nicht direkt miteinander kommunizieren. Sie sollten durch ein GUI oder Gateway orchestriert werden.


## 2. Jeder Service läuft in eigenem Prozess / auf eigener Plattform
Jeder Service läuft in einem eigenen Prozess / Plattform.
- Ermöglicht die Verwendung unterschiedlicher OS, Programmiersprachen, technologien etc.
- Laufen typischerweise in einem virtualisierten [[Container]]

Dadurch laufen die Services in echter Parallelität als [[Verteilte Applikation]].
Dadurch entstehen auch folgende Herausforderungen:
 - Kommunikation über das Netzwerk
 - Skalierung
 - Latenz
 - Ausfall
 - Locking

Durch die echte Parallelität kann jedoch auch die Systemleistung erhöht werden.

=> Komplexität des Systems erhöht sich.


## 3. Leichtgewichtige Kommunikation (meist RESTfull/http/JSON)
Derzeit sind JSON-basierte REST Schnittstellen sehr beliebt, da diese sehr einfach sind.

Jedoch sind JSON-Schnittstellen im Vergleich zu binären Protokollen (RMI, gRPC) nicht mehr so leichtgewichtig.

Jedoch bietet HTTP(s) trotzdem noch einige Vorteile:
- Authentifizierung und Verschlüsselung kommt "gratis"
- Gute Akzeptanz im Operation, **battle tested**

## 4. Voneinander unabhängig deploybar (und somit auch Releases)
Microservices sind eigneständige Projekte (Git) und Releaseeinheiten und werden erst durch **gemeinsame Orchestrierung** zu einer Applikation.
- Felxibles entwicklen
- Änderung können mit kleinem Risiko durchgeführt werden.
- Erweiterung können einfach hinzugefügt werden [[Open Closed Principle]]

Durch die Granularität der Deploymenteinheiten können Microservices auch einzeln (re)deployed werden.
- Applikation muss mit **nicht Verfügbarkeit** der Services umgehen können.

Dadurch, dass es viele kleine Services gibt, steigt auch die Ausfallquote.
-> [[Resilienz]] wird somit sehr wichtig.

## 5. Automatisiertes Deployment (DevOps, PaaS, IaaS)
Da jeder Microservice einzeln deployed werden muss, steigert sich auch die benötigte Zeit sowie die Fehleranfälligkeit, falls dies von Hand ausgeführt wird.

Dadurch wird die Automatisierungdes Deployments essenziell.