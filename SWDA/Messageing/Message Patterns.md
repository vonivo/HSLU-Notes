Es existieren verschiedene Arten von Messages welche von eine [[Message Broker]] wie [[RabbitMQ]] verwendet werden können.

- **Synchron/Asynchron**: Die [[Messaging|Message]] erwartet eine/keine Antwort
- **Observe/Consume**: Die Message wird nur "überwacht/gelesen" und andere Consumer sehe dies auch oder die Message wird konsumiert und aus der Queue entfernt.
## Fire and Forget
Bei Fire and Forget wird eine asynchrone Message verschickt, welche **nicht** konsumiert wird. Der Sender interessiert sich nach dem Absenden nicht mehr für die Message.

Ähnelt [[Publish-Subscribe]]


## Winner take all
Bei Winner takes it all wird eine asynchrone Message verschickt, jedoch wird die Message konsumiert. Dass heisst, auch wenn mehrere Consumers auf dieselbe Queue hören wird sichergestellt, dass nur ein Consumer die Nachricht erhält.

Wird meistens mit mehreren Consumers angewendet, welche die Last untereinander aufteilen.

## Request Response
Bei der Request Response ist, wird eine synchrone Message verschickt. Auch hier wird die Message konsumiert und der Sender erhält eine Antwort.


## Synchroner Observer
Dieses Pattern beschreibt einen synchronen Request, welcher nicht konsumiert wird.
Der Sender ist dabei aber nur an der Antwort eines spezifischen Services interessiert. Alle anderen Services können die Nachricht trotzdem lesen, jedoch antwortet nur der eine Service.


## Dead Letter Queue
Die Dead Letter Queue ist ein Ort, wo alle nicht zustellbaren/verarbeitbaren Messages landen.

Die Dead Letter Queue kann wie ein Log verwendet werden um fehler im System zu identifizieren.

