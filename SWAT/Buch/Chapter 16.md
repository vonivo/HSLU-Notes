**Where does space-based architecture get its name from?**
Der Name kommt von dem Memory-Speicherplatz der von der Architektur benötigt wird.

**What is a primary aspect of space-based architecture that differentiates it from other architecture styles?**
Der Hauptunterschied ist, dass die "Main-Data-Source" (DB) zeitlich komplett entkoppelt ist vom Rest der Applikation. Sprich alle Reads und Writes passieren asynchron.

**Name the four components that make up the virtualized middleware within a space-based architecture**
1. Data-grid
2. Processing-grid
3. Messaging-grid
4. Deployment-Manager

**What is the role of a data writer in a space-based architekture**
Ein Data-Writer ist dafür zuständig die Änderungen an Daten, welche ihm über Messaging und einen Data-Pump zur Verfügunggestellt werden, in der Datenbank zu persistieren.

**Under what conditions would a service need to access data in a database through the data reader**
Es gibt drei Szenarios, in welchem Daten von der DB gelesen werden müssen:
1. Crash aller Nodes einer Processing-Unit
2. Redeployment aller Processing-Units
3. Fetch von archivierten Daten.

**Does a small cache size increase or decrease the chances for a data collision?**
Durch eine kleine Cache-Size wird die Wahrscheinlichkeit einer Data-Collision erhöht.

**What is the difference between a replicated cache and a distributed chache? Which on is typically used in space-based architecture?**
Der Replicated-Cache wird mehr genutzt.
Beim Distributed-Cache existiert eine Instanz welche der Cache darstellt. Alle Nodes welche etwas vom Cache benötigen fragen diesen über Netzwerk an(z.B. Redis)

Bei einem Replizierten Cache wird der Cache auf alle nodes repliziert und synchronisiert. Darum wird bei einem Read keine Anfrage über das Netzwerk benötigt.

**List the three most strong supported architecture characteristics in space-based architecture**
1. Scalability
2. Elasticity
3. Responsiveness

**Why does testability rate so low for space based architecture?**
Diese Architektur wählt man, weill man Scalaability, Elasticity und Responsiveness umbedingt benötigt. Diese Punkte zu testen ist jedoch extrem schwierig und fast nur in der Produktion wirklich machbar. Daher hat die Architektur nur ein Stern bei Testbarkeit.


