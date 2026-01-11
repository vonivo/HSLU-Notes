Durch die Realisierung von [[Microservice Architektur]] stellen sich neue Herausforderungen die jeder [[Microservice]] zu bewältigen hat.
1. Durchgängiges, konsistentes, einheitliches [[SWDA/Software Architektur/Architekturen/Microservice/Logging|Logging]] von fachlichen und systemtechnischen Ereignissen
2. Durchgängige Verfolgbarkeit ([[Tracing]]) von (Geschäfts-)Prozessen über mehrere Schritte in verteilten Services und Systemen.
3. Überwachung der Performance ([[Metrics]]) und der Ressourcen zur Feststellung von Engpässen in einzelnen (Micro-)Services oder bei (Teil-)Ausfällen.

## Vergleich Klassische Architektur
Einfacher Aufruf der Businessfunktionalitäten
- Oft sequenzieller, synchroner Ablauf
- Alles oder nichts Semantik (LUW)

Einfache Welt, weil:
- Einfaches, zentrales Logging
- homogene Plattformen, Sprachen und Frameworks
- Zentralisierung der Prozesse und Daten


## In Microservices
- Vielzahl nicht sequenzieller asynchroner Aufrufe verteilt auf Systeme.
- Häuffig über Queues entkoppelte.
- Einzelen Services können ausfallen etc.

**Herausforderungen**
- Logging findet auf verschiedenen Systemen, Sprachen und Frameworks statt.
- Start verteilte Datenhaltung, Netzwerkinfrastruktur.
- Durch lose [[VSK/Modularisierung/Kopplung|Kopplung]] verliert man etwas die Nachverfolgbarkeit von Businessprozessen.
- 