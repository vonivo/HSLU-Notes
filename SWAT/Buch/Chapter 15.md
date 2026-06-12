**Name four differenes between events and messages**
1. Events beschreiben ein Aktion die durchgeführt wurde.
2. Evetns sind meistens 1:n
3. Events erwarten keine Antwort
4. Events nutzen meist topic oder stream und messages queues oder messaging services

**What's the difference between an initiating event and a derived event?**
Der Initiation Event ist der ursprüngliche Event welcher ins System hineinkommt. Ein derived Event wird als Reaktion auf einen Initiating-Event oder Derived-Event erstellt.

**What is a poison event?**
Ein Poison-Event ist ein Event welcher das System welcher das System nicht mehr verlässt, da er einen Loop bildet.

**Can an event processor trigger multiple derived events? If so, why would you want to do this?**
Ja ist möglich. Das wird gemacht, um die Events zu einem gewissen Punkt atomar und selektiv zu halten, damit nicht jeder Processor auf jeden Event horchen muss und dann für sich entscheiden, ob es relevant war. Mit kleineren Events horcht der Processor nur auf die für ihn relevanten Events.

**Why would you trigger an event from an event processor that no other event processor responds to?**
Dies ist eine gängige Taktik um Extensions-Points zu generieren, welche das System dynamisch und lose erweiterbar machen.

**What are some of the negative trade-offs in using asynchronous processing?**
- Errorhandling ist schwierig
- Ende nicht absolut bestimmbar
- Prozess neustarten ist schwierig

**Describe the Swarm of Gnat antipattern and explain why you shoudl avoid it.**
Dieses Antipattern beschreibt das Verhalten, wenn ein Event sehr viele sehr kleine derived Events auslöst welche widerum kleine Events auslösen. Dadurch ist es schwierig einen Überblick zu halten und zudem kann das System überlastet werden.

**Give two primary reasons why event driven architecure is highly responsive and has great preformance charakteristik**
Durch asnychronität wird das System repsonsiver. Da nicht auf die vollständige Verarbeitung gewartet werden muss. Zusätzlich kann die performance mit Competing-Consumer sehr gut erhöht werden.

**What are some of the techniques for preventing data loss when sending and receiving messages from a queu?**
1. Syncrhonous Send and Persistante Queues
2. Client acknowledge mode
3. Last participant support

