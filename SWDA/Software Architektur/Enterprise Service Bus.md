---
aliases:
  - ESB
---
Man kombiniert die Idee von Services ([[Service Oriented Architektur|SOA]]) und Messaging ([[Message- oder Event-Driven Architekturen]]).

Die Services werden von einem Message-Bus-System verbunden, dass es erlaubt verschieden Topics und Queues zu erstellen.

- Services können selbständig für Topics registrieren
- Services können Messages publizieren

![[ESB.png]]=> Es entsteht eine lose Kopplung
=> Reaktionen können auch asynchron erfolgen



## Vorteile
- Meistens asynchrone Kommunikation – **schneller**.
- Fire&Forget – **einfacher**
- Bei einem Ausfall wird (persistent) gequeued – **robuster**
- Neue Applikationen können sich frei registrieren – **flexibler**
- Das System kann elegant skalieren – **leistungsfähiger**

## Herausforderungen
- Welche Topics werden erstellt
- Welche Messages / Events existieren
- Welche Granularität haben die Messages
- Verfügbarkeit des ESB (Single Point of Failure)