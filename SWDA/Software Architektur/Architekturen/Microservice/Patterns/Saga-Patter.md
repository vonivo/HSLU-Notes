Es existiert eine [[Microservice Architektur]] mit einer einzelnen Datenbank pro [[Microservice]].
Falls es nun [[Transaktion]] gibt, welche sich über verschiedene Services erstrecken wird ein Mechanismus zur Implementierung von Transaktionen benötigen.

Es sollte keine [[Transaktion#Verteilte Transaktion|verteilte Transaktion]] genutzt werden, da diese Synchronität das System lahmlegen kann.

**Lösung**
Es wird eine Saga implementiert. Ein Saga ist eine Sequenz von lokalen Transaktionen, welche bei Erfolg eine [[Messaging|Message]] versendet, welche dann eine neue Transaktion in einem anderen Service triggert.
Wenn eine lokale Transaktion fehlschlägt, wird eine [[Messaging|Message]] versendet, welche dann Kompensationsmechanismen in den einzelnen Services auslöst.

Es exisiteren zwei Arten von Saga:
- **Choreography**: Jede lokale Transaktion versendet selbst domain events welche weitere aktionen triggert.
- **Orchestration**: ein Orechstrator-Objekt sagt den einzelnen Services welche lokale Transatkion ausgeführt werden soll.

## Choreography
![[Saga_Choreographie.png]]
1. Der `Order-Service` erhält einen `POST /orders`-Request und erstellt eine `Order` mit dem Status `PENDING`.
2. Der `Order-Service` versendet einen `Order created` event.
3. Der `Customer-Service` versucht durch den Event die totale Summe zu reservieren
4. Der `Customer-Serivce` versendet einen Event welcher das Result seiner reservierung beinhaält.
5. Der `Order-Service` setzt die `Order` auf `APPROVED` oder `REJECTED` basierend auf dem erhaltenen Event.

## Orchestrator
![[Saga_Orchestrator.png]]
1. Der `Order-Service` erhält einen `POST /orders`-Request und erstellt eine `Order-Orchestrator`.
2. Der `Order-Orchestrator` erstellt ein `Order-Object` mit dem Status `PENDING`.
3. Der Orchestrator senden eine `Reserve Credit`-Event an den `Customer-Service`.
4. Der `Customer-Service` versucht den Betrag zu reservieren.
5. Der `Customer-Service` sendet das Resultat zurück an den `Order-Service`.
6. Der `Order-Orchestrator` setzt die `Order` auf `APPROVED` oder `REJECTED` basierend auf dem erhaltenen Event.

