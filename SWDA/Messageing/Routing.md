In einem [[Messaging|Message]]-basierten System kommunizieren [[Microservice Architektur|Services]] nicht direkt miteinander, sondern kommunizieren über einen [[Message Broker]].

Dadurch muss ein Service den Empfänger nicht kennen.

>[!Definition]
>Eine Message wird anhand ihrer Properties/Metadaten im Message-Header in die richtige Queue geroutet.

Damit dieses Routing effizient aufgebaut werden kann und nicht für jede Queue eine eindeutige Kennung existieren muss existiert das **Patternmatching**

## Pattern-Matching
Um Pattern-Matching nutzen zu können, braucht es Namespaces. Diese können auf mehrere Arten eingeführt werden:
- Labels im Message-Header
- Hierarchische Struktur der Message.

Beispiel einer hierarchischen Struktur:

| Messagename     | routing-table   |
| --------------- | --------------- |
| create-customer | customer.create |
| delete-customer | customer.delete |
| create-product  | product.create  |
| delete-product  | product.delete  |

Über diese Hierarchie und Wildcard `*` kann nun ein Routing gemacht werden:
![[Routing.png]]


## "Synchrone" Message
Es können auch synchrone Messages versandt werden. Hierfür wird in der 1. Nachricht eine temporäre Reply-Queue angegeben, an welcher der Aufgerufene antwortet. Nachdem die Antwort empfangen wird, kann die Queue wieder gelöscht werden.
![[ReplyTo.png]]

## Zuverlässige Auslieferung
Es gibt verschiedene Möglichkeiten, warum eine Message nicht ausgeliefert werden kann.

Messagingsysteme können Nachrichten mehrmals zustellen, im Fehlerfall. Dafür müssen sie jedoch wissen ob die Nachricht angekommen ist.

Der Empfänger kann deshalb eine Acknowledgment-Nachricht (**ACK**) versenden, wenn die Message erfolgreich angekommen ist.

Diese ACK-Message können in beide Richtungen verwendet werden:
- Das Messaging-System sagt, dass die Nachricht des Producers angekommen ist.
- Der Consumer sagt, dass er die Nachricht erhalten/verarbeitet hat.


ACK-Messages garantieren [[Auslieferungsgarantien|At Least Once]].
Ohne ACK-Messages ist nur At Most Once garantiert.

![[AtLeastOnce.png]]