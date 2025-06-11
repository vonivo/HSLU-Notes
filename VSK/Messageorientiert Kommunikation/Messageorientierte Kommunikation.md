>[!Definition]
>Messageorientiert Kommunikation ist Kommunikation mittels **expliziter** Messages von einem **Sender** zu einem oder mehreren **Empfängern**.

**Verwendung**
- Nebenläufige und parallele Programmierung (Actor-Model)
- Interprozesskommunikation (z.B. UNIX-Sockets)
- Verteilte Systeme

**Abgrenzung zu**
- [[VSK/RPC/RPC|RPC]]
- Streaming
- Shared-Memory

## Wie wird Messageorientierte Kommunikation spezifiziert

**Zuverlässigkeit**
Können Messages verloren gehen

**Reihenfolge**
Kommen die Messages alle in der vorgehesenen Reihenfolge an?

**Anzahl Empfänger**
Wie viele Empfänger gibt es?
- Unicast (1-1)
- Broadcast/Multicast (1-n)
- Client Server (n -1)
- Peer2Peer (m - n)

**Ausführungszeitpunkt**
Werden die Messages **[[Synchrone Kommunikation|synchron]]** oder **[[Asynchrone Kommunikation|asynchron]]** übertragen?

**Sicherheit**
Ist die Kommunikation offen oder Zugangsgeschützt, Verschlüsselung