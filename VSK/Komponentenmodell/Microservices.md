>[!Definition]
>"In short, the microservice architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API. These services are built around business capabilities and independently deployable by fully automated deployment machinery. There is a bare minimum of centralized management of these services, which may be written in different programming languages and use different data storage technologies." (James Lewis and Martin Fowler, 2014)

**Ziel:** bessere Aufteilung auf verschiedene Entwicklungsteams (Konzentration auf Fachdomäne)

**Eigenschaften**
- **Aufteilung in Services:** Anwendung in kleine Services, welche als Komponenten verwendet werden
- **Schichten übergreifend**: enthält alle Schichten einer Funktionalität
- **Unabhängiges Deployment:**
- **Kommunikation über Netzwerk:** REST, MQ, SOAP, etc.
- **Entkopplung:** Microservice nur über Schnittstelle bekannt.
- **Technologische Entkopplung:** pro Microservice kann z.B. eine andere Sprache verwendet werden.

## [[Komponentenmodell]]
| Eigenschaft                    | Inhalt                                                                                                                                                                                                                                  |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Schnittstellendefinition       | OpenAPI                                                                                                                                                                                                                                 |
| Kommunikation und Verteilung   | - HTTP Ressourcen API (REST)<br>- Verteilung über virtuelle und physische Systeme möglich                                                                                                                                               |
| Komposition und Auffindbarkeit | - Komposition mittels Docker-Compose<br>- Automatische Vergabe von Hostname/Port an Service-Anbieter.<br>- Automatische Übergabe von Hostname/Port an Konsumenten z.B. mit Umgebungsvariablen<br>- Isolation durch unabhängige Prozesse |
| Deployment                     | - Gebündelt mit HTTP-Server und allen Abhängigkeiten als Container Image<br>- Abgelegt in Binary-Repo                                                                                                                                   |

**Kommunikation:**
- Muss Interprozess-Kommunikation sein
- "often an HTTP resource API"

**Schnittstellendefinition Beispiel:**
```yaml
openapi: "3.0.2"
info:
  title: "TransformApi"
  version: '1.0'
  description: "Interface for text transformations."
  license:
    name: "Apache License 2.0"
    url: "http://www.apache.org/licenses/LICENSE-2.0"
paths:
  /transform:
    get:
      summary: "Applies transformation to input"
      description: "Applies transformation to input"
      parameters:
      - name: text
        in: query
        description: "Contains text to transform"
        schema:
          type: string
```

**Verbinden von Services:**
- Regulär via Hostname/Port
  - Statische Zuweisung von Hostname/Port per Konfig File nicht praktikabel
- Umgebung sehr variablel

Möglichkeiten zur Konfiguration: 
- Komposition mittels Skripts (selten) oder Orchestrierungstools (Docker Compose, Kubernetes)
- Export: Orchestrierungstools/Skripts vergeben Hostname/Port an Container z.B. mittels Umgebungsvariablen
- Import: Orchestrierungstools/Skripts injizieren Hostnamen/Port in Konsumenten z.B. mittels Umgebungsvariable oder Programmargumenten

**Möglichkeiten zum Deployment**
- Kein eigener Prozess
  - Normale Webservices im Applikationsserver
- Bündeln mit vollwertigem Applikationsserver
  - Komplex benötigt viele Ressourcen
- Ausführbares JAR inklusive Server
  - nicht Technologie neutral
- Container-Images mit allen Abhängigkeiten