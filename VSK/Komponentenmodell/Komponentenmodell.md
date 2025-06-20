>[!Definition]
>Eine Software-Komponente ist ein Software-Element, das zu einem *bestimmten Komponentenmodell* passt und entsprechend einem Composition-Standard ohne Änderungen mit anderen Komponenten verknüpft und ausgeführt werden kann.

Ein Komponentenmodell:
- Legt grundlegende  Eigenschaften der Komponenten fest,
- Erstellt einen Rahmen für die Entwicklung, oft in Zusammenhang mit der Laufzeitumgebung,
- Ist Basis für die Interaktion zwischen Komponenten.
- Konkrete Ausprägung des Paradigmas der Component-Based-Entwicklung
- Neben Form und Eigenschaften einer Komponente definiert eine Komponentenmodell auch ein [[Interaction-Standard]] und einen [[Composition-Standard]]

**Beispiele**
- Enterprise Java Beans
- OSGI
- CORBA

## Aufbau
![[Komponentenmodell1.png]]Weiter Eigenschaften können: 'Sicherheit', 'Logging', 'Monitoring' sein.


## Beispiel
Beispiel für das Logger-Projekt:

| Eigenschaft                    | Inhalt                                                                  |
| ------------------------------ | ----------------------------------------------------------------------- |
| Schnittstellendefinition       | Java-Interfaces, [[gRPC]]                                               |
| Kommunikation und Verteilung   | Lokal: SharedMemory / Methodenaufrufe<br>Verteilt: [[RPC]] (via TCP/IP) |
| Komposition und Auffindbarkeit | - Service Provider<br>- Spring<br>- Hostname / Port                     |
| Deployment                     | Container und Jar                                                       |
