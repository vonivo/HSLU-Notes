**Why are services in service based architecture called domain services**
Sie werden so gennant, da ein Service oft eine ganze Domäne/Teildomäne abdeckt.

**Name two common risks associated with service-based architecture**
1. Changes am DB-Schema
2. Zu viel Inter-Service-Kommunikation
3. Zu viele Domain-Services (im Idealfall > 12)

**Which databse topologies (monolithic, domain and dedicated) can you use with service based architecture**
Es gibt 3 verschiedene Arten:
1. Eine monolithische Datenbank für alle Services
2. Eine Datenbank pro Domäne -> kann für mehrere Services sein.
3. Eine Datenbank pro service
Kombinationen sind natürlich auch möglich.

**What techniques can you use to manage database changes wihthin a service-based architecture**
Es gibt die Möglichkeit eine Shared-Library für die Persistenzschicht zu nutzen. Diese Schicht wir am besten logisch weiter partitioniert (z.B. common, customer, order, etc) in den einzelen Services werden dann nur die Partitionen inkludiert welche wirklich genutzt werden. So können Services vor Changes geschützt werden, welche sie nicht brauchen.

**Do domain services require a container such as Docker to run**
Nein, sie können auch als normale Applikationen deployed werden.

**Which architecture characteristics does the service based architecture supports well**
Die Service-Based-Architektur ist ein allrounder und unterstützt dabei viele Charakterisitken gut. So z.B. Maintainablilty, Testability, Deployabilit und Evolvability.

**Why isn't elasticcity typically well supported in a service-based architecture?**
Elastizität ist nicht gut unterstützt, da es eigentlich pro Service immer nur eine Instanz geben sollte. Sprich es kann kein On-Demand-Scaling etc. geben

**How can you increase the number of architecture quanta in a service-based architecture?**
Die Anzahl der Architektur-Quanta kann erhöht werden indem pro Quanta eine eigene DB und ein eigenes UI deployed werden.

