Zentrale Herausforderung ist die **Unabhängigkeit** der einzelnen [[Microservice|Microservices]].
Die Abhängigkeiten der Services entsteht primär durch die Kommunikation der Services. Darum sollte die Kommunikation der Services möglichst **minimiert** werden.
- Kopplung wird von "compiletime" ins deployment verschoben.


Für die Betrachtung hilft eine Unterteilung in zwei verschieden Kommunikationen:
- Client zu (Port)Service
- Service zu Service

## Client zu (Port)Service
Clients (z.B. UI) mit den (Port-)Microservices.

In der Praxis wird hier oft REST-basierende Kommunikation mit JSON und XML verwendet.

Mehrheitlich wird **synchrone** Kommunikation verwendet, weil der Client unmittelbar Feedback erwartet.

Damit ein Client nicht alle Services kennen muss, wird oft ein **[[Gateway]]** verwendet, welcher eine zusammengefasst einheitliche Schnittstelle anbietet.

## (Port)Service zu Service
(Inter-)Kommunikation zwischen Microservices (Port~ oder Kern~).

Direkte Kommunikation zwischen Services ist möglich, sollte jedoch, wenn immer möglich, vermieden werden.
- Direkte Kommunikation bedeutet starke [[Kopplung]], sowohl im Design als auch zur Laufzeit

Um diese Kommunikation zu vermeiden, kann [[Messaging]] verwendet werden.
Es werdend dabei **Queues** und/oder **Topics** verwendet, um die Kopplung zu minimieren.
- Wenn immer möglich **asynchron**
- Events/[[Messaging|Messages]] und Commands

Neue Services können sich extrem elegant und lose gekoppelt registrieren, und so neue Funktionalität dynamisch ergänzen. (siehe [[Enterprise Service Bus|ESB]])