Bei synchroner Kommunikation befindet sicher der Sender in **Wartezustand** bis er seine Nachricht vollständig verarbeitet wurde.

![[synchron.png]]
**Beispiel**
- [[VSK/RPC/RPC|RPC]]
- Anfrage einer Ressource mittels HTTP-Protokoll und synchroner Auslieferung

>[!warning]
>Die Verarbeitungszeit sollte möglichst kurz gehalten werden. ([[Thread|Threads]] oder Non Blocking I/O)

