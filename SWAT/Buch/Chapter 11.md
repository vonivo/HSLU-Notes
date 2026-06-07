**How does the modular monolith differ form the n-tiered layered architecture**
Der Modulith unterscheidet sich von einem Layered-Monolith dadurch, dass die Top-Level-Partitionierung anhand der Domäne / Subdomäne ist und nicht anhand der Technologie.

**Describe the difference between the peer-to-peer and mediator approaches when communication between modules.**
Bei einem P2P Ansatz kommunizieren die Module direkt miteinander. Damit dies sauber funktioniert, müssen saubere Schnittstellen definiert  sein.
Ein anderer Ansatz ist der Mediator Approach, welcher die Verantwortung der Ablaufsteuerung übernimmt. Dabei kommuniziert jedes Modul nur noch mit dem Mediator.
Die Kopplung wird so nicht zwingend reduziert sondern eher verschoben.

**What are the common risks associated with the modular monolith architectural style?**
1. Die Applikation wird zu gross und dadruch weniger warbar.
2. Die Applikation errodiert über Zeit durch ungewünschte Abhängigkeiten
3. Zu viel unschöner Code-Reuese
4. Zu viel Intermodul-Kommunikation


**Name three primary strengthsof the modular monolith and wehn you shoud consiert using it.**
1. Einfachheit
2. Tiefe Entwicklungskosten
3. Gut  wenn änderungen Domain-Based sind
Der Modulith eignet sich gut als Startpunkt oder wenn keine / wenige spezifische Anforderungen an die Operations gestellt sind. (Vor allem bei kleinen Applikation gut geeignet).
Gut geeignet wenn man nach DDD arbeiten will.