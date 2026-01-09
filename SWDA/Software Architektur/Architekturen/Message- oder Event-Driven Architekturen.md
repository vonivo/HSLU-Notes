>[!Definition]
>Bei Message- oder Event-Driven Architekturen wird das Prinzip von Events (vgl. [[Observer]]) auf eine höhere Stufe angewendet.

Der Hauptvorteil von Message oder Event-Driven Architekturen ist die lose [[VSK/Modularisierung/Kopplung|Kopplung]]:
- Der Sender muss den Empfänger nicht kennen.
- Es muss nur über die Semantik der Event Einigkeit herrschen.

Bei [[Service Oriented Architektur|SOA]] manifestiert sich die Kopplung der Services meist in synchroner Kommunikation. Jedoch müssen oft nicht alle Aktionen synchron ausgeführt werden.


=> Wo bisher persistente, klassische Datenbanken für den «Informationsaustausch» verwendet wurden, können Message-Systeme diese mindestens* unterstützen.
- Systeme deutlich und stärker entkoppeln und vereinfachen.
- Unterstützen mehrheitlich auch Persistenz.