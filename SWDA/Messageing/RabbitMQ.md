>[!Definition]
>RabitMQ ist ein leichtgewichtiger, opensource [[Message Broker]].
>RabbitMQ unterstützt viele Protokolle wie AMQP sowie verschiedene Programmiersprachen.

**Wichtige Konzpete**
- **Exchange:** Ein Exchange nimmt [[Messaging|Messages]] entgegen und verteilt diese auf Queues basierend auf Routing-Rules.
- **Queue**: Ein Warteschlange in welcher Messages platziert werden, welche von Consumers abgearbeitet werden.
- **Bindings**: Eine Konfiguration welche Exchanges zu einer Queue mappt und das [[Routing]] definieren.

## Exchange
RabbitMQ kennt drei Exchange Typen:
- **Direct**: Nutzt den Queue-Namen als Binding-Pattern
- **Fanout**: Verteilt alle Messages zu allen an den Exchange gebunden Queues ohne Routing.
- **Topic**: Nutzt einen Routing-Key und Pattern-Matching um Messages auf die Queues zu verteilen.
 ![[RabbitMQ.png]]


**Verbindung**
Um eine Verbindung zu RabbitMQ zu erhalten werden zwei Komponenten genutzt:
- **Connection:** [[TCP]]-Verbindung zu RabbitMQ. Es wird pro Prozess eine Verbindung genutzt, welche offen bleiben sollte.
- **Channel**: Virtuelle Verbindung innerhalb einer Connection. Channels sind leichtgewichtig, trotzdem wird empfohlen den Channel ebenfalls offenzulassen,
  jedoch sollen für unterschiedliche Threads unterschiedliche Channels verwendet werden.
