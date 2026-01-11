---
aliases:
  - Message
---
Ein Message-basierte [[Microservice Architektur|Microservice Architektur]] kommuniziert, indem verschiedene Messages durch das System geschickt werden.

Messages können dabei eine Antwort oder weitere Messages auslösen.


### Message
Eine Informationseinheit, welche durch das System gesendet wird. Es besteht aus eine Header mit **Metadaten** und einem Body, welcher **Date** (meist in binary) enthält.

### Producer
Ein Aktor, welcher Messages erstellt und versendet.

### Consumer
Ein Aktor, welcher Messages erhält und liest.

### Queue
Ein Collection, welche Messages in eine Warteschlange einfügt welche danach bei Consumer erhalten werden können.

Ein Message-basiertes System nutzt normalerweise ein Messaging-System, welches oft als [[Message Broker]] oder [[Persistente Kommunikation|Message Oriented Middleware]].
![[MessageQueues.png]]

## Vorteile von Messaging
- **Resilienz**: Messages gehen nicht verloren, wenn das Netzwerk down ist. Messages werden gebuffert und dann wieder versandt.
- **Fehlertoleranz:** Wenn ein Service crasht oder eine Message nicht verarbeiten kann, kann die Message erneut ausgeliefert werden.
- **Entkoppelt**: Die kommunizierenden Services kennen sich gegenseitig nicht.
- **Effizient und Skalierbarkeit**: Volle Asynchronität ist ein Schlüsselfaktor für Responsivenes und Skalierbarkeit. Durch Queues werden Producer und Consumer entkoppelt, und die Distribution von Messages an mehrere Consumers erlaubt.


## Messageorientiertes Denken
- In Messages nicht in Services denken.
- Dataflow zwischen Services soll nicht direkt definiert werden.
- Services sollten nichts über andere Services wissen.

Businessrequirements können in einzelen Aktionen heruntergebrochen werden. Diese Aktionen können helfen die Nachrichten zu identifizieren.![[MessageCentric.png]]

**Beispiel**
![[MessageCentric2.png]]

## Skalierbarkeit
Auch mit Messaging kann eine Queu überlastet werden. Dann gibt es verschiedene Lösungen:
1. Wir erhöhen die Anzahl an Consumer welche auf die Queue hören.
2. Wir nutzen Backpressure-Strategien:
	- **Synchronous Backpressure:** Producer können erst wieder senden, wenn die Queue noch Platz hat: (ähnlich wie [[Semaphore]])
	- **Load Shedding**: Bei Überlast werden neue Nachrichten abgeweisen oder verwofen.
	- **Flow Control**: Automatische regulierung des Datenfluss zwischen Producer und Consumer.