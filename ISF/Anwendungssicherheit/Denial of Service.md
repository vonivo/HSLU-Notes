Denial of Service ist, wenn ein System aufgrund hoher Last unerreichbar ist / zusammen bricht. Diese Attacke operiert auf der Transpor-Schicht des  [[OSI Referenzmodell|TCP-IP-Stack]].

**Distributed-Denial-Of-Service** ist, wenn der Server von verschiedenen Systemen belastet wird.


**Beispiel**
Distributed Reflection Denial of Service:
![[Pasted image 20250118174242.png]]
An viele unterschiedliche Server wird eine TCP-Anfrage gesendet, mit der Adresse des Opfers als Absender. So kommt danach von jedem Server ein "SYN-ACK" an das Opfer zurück.


## Schutz
Jedes System bricht irgendwann zusammen. Falls dies eintritt, geht es darum, dass dabei keine bleibenden Schäden entstehen und das System schnell wieder verfügbar ist.
- Beschränkung der Anzahl (Web)-Requests pro Zeiteinheit /IP
- Sicherstellen, dass der Flaschenhals weit vorne (z.B. Firewall) auftritt.
- Sicherstellen, dass das System sich nicht selbst überlastet, durch Freigeben nicht mehr verwendeten Ressourcen, vermeiden von unendlichen Loops.
- Disaster Recovery Plan.