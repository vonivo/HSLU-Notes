Ziel des Remote-Procedure-Calls ([[RPC]]) ist der analoge Aufruf einer Remote-Function wie einer lokalen Funktion:
![[VSK/img/rpc.png]]
**Ablauf:**
1. Client Ruft Remote-Function auf.
2. Clinet-Stub [[(De)Serialisierung|serialisiert]] Nachricht.
3. Senden über Netzwerk.
4. Server OS gibt Nachricht an Stub weiter.
5. Server-Stub [[(De)Serialisierung|deserialisiert]] die Nachricht.
6. Stub ruft Funktion auf.
![[rpc_ablauf.png]]