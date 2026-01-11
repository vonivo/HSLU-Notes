>[!Error]
>Microservices und Transaktionen vertragen sich nicht.

- Transaktionen schaffen eine enge, semantische [[Kopplung]]. -> [[Microservice|Microservices]] will gerade das vermeiden.

**Lösung**: Keine Globale Transaktionen.
- Transaktionen sollen aufgebrochen werden: [[Saga-Patter]]
- Zu stark getrennte Services wieder zusammenfassen
- Transaktionen minimieren.


## Transaktionen in [[Monolithische Architektur|Monolith]]
- Praktisch durch RDBMS geschenkt.
- [[Transaktion#Verteilte Transaktion|Two-Phase-Commit]] kein Problem

## Transaktionen in [[Service Oriented Architektur|SOA]]
- Transaktionen werden möglichst auf einen Service beschränkt.
- Aufgrund der passenden Granularität relativ gut möglich.


## Transaktionen mit Microservices
- Genauer überlegen welche (temporalen, nicht kritischen) Inkonsistenzen ([[Eventual Consistency]]) man zulassen kann.

Teile eines bisher strikt synchronen Ablaufes werden bewusst herausgebrochen und
neu asynchron, unabhängig, und zu einem späteren Zeitpunkt ausgeführt