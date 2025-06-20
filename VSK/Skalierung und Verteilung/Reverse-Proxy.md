>[!Definition]
>Ein **Reverse-Proxy** ist eine vorgeschaltete Middleware, welche Anfragen auf verschiedene Instanzen einer Serveranwendung verteilt.

![[ReverseProxy.png]]
Ein Reverse-Proxy bietet:
- **[[Load-Balancing]]**: Last wird auf mehrere Instanzen verteilt, sodass keine Instanz überlastet ist, solange noch andere Instanzen Kapazität haben.
- Weitere Funktionen:
	- Verschlüsselung
	- Monitoring
	- Metriken
	- Kompression

**Beispiele**
- [[HAProxy]]
- Webserver wie Apache / Nginx
- Traefik


Sollen mehrere aufeinanderfolgende Request unabhängig der TCP-Verbindung zur gleichen Serverinstanz geleitet werden, muss der Reverse-Proxy das Protokoll inspizieren können.
![[ReverseProxy2.png]]

## Ausfallsicherheit
### Server-Node
Damit das Load-Balancing Anfrage nicht an eine Instanz weiterleiten, welche nicht erreichbar ist, werden Health-Checks ausgeführt.

Typsiche Health-Checks:
- TCP-Verbindung aufbauen (Transport-Schicht)
- HTTP-Request (Anwendungsschicht)
- Ausführung eines Agents auf Server

### Proxy-Instanz
Es ist wichtig, dass immer mehrere Reverse-Proxys eingesetzt werden, da der Proxy ansonsten ein Single-Point-Of-Failure darstellt.

- Kombination mit Hochverfügbarkeitslösungen (keepalived) und Floating-IPs
- Switch auf anderen Proxy bei Ausfall.