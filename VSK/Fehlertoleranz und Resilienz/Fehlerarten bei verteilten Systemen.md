
**Zielsystem nicht erreichbar**
- Daten und Messages können nicht verschickt werden.

**Auslassungsfehler: Falsche Reihenfolge der Daten / Messages**
- Datenkorruption / Programmfehler

**Abrupter Verbindungsunterbruch durch Netzwerkausfall**
- Verlust von Daten / Messages.

**Abrupter Verbindungsunterbruch durch Serverausfall**
- Verlust von Daten / Messages.
- Korrupte Daten

## Beispiel bei [[VSK/RPC/RPC|RPC]]
![[RPC_Fehler.png]]
1. Server nicht verfügbar.
2. Request geht verloren.
3. Server crashed.
4. Reply geht verloren
5. Client crasht während der Übertragung.
