Ein Monitor ist ein Kontrollelement der [[Interprocess Communication]]. Es ist eine higher-level Synchronisationsmöglichkeit als [[Mutex]] und [[Semaphor|Semaphore]]. 

Ein Monitor ist eine logische Gruppierung von [[Datenstruktur|Datenstrukturen]], [[Methode|Methoden]], Programmabschnitten und/oder Ressourcen. 

Es kann sich immer nur ein Prozess zeitgleich in einem Monitor befinden. 

Ein Monitor kann intern [[Mutex]] und [[Semaphor|Semaphore]] verwenden, jedoch macht das die Programmiersprache und nicht der Programmierende. Dadurch ist es weniger fehleranfällig. 
- Jedoch hat nicht jede Sprache Monitore

