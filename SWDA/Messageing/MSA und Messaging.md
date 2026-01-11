Wie soll ein Service in einer [[VSK/Komponentenmodell/Microservices|Microservice Architektur]] aufgerufen werden?
```java
double MyService(double a, int b)
```

- Dieser Aufruf ist nicht erweiterbar.
- hohe [[Kopplung]]

Dieser "[[VSK/RPC/RPC|RPC]]"-Call ist noch nicht wirklich MSA orientiert. In einer MSA gibt es eigentlich keine Methoden-Aufrufe sonder **Messages**.

```java
Response MyService(Request a)
```
- Das `Request` Objekt kann serialisiert werden.
- Der Aufrufer erwartet eine Antwort, welche auch serialisiert werden kann.

=> Durch die Synchronität existiert jedoch noch eine Kopplung welche für [[Messaging]] nicht zwingend optimal ist.


**Lösung**
```java
void MySerivce(Request request)
```
- [[Asynchrone Kommunikation|Asynchronität]]
- Request wird in einer Message-Queue platziert.
- Wenn der Service eine Antwort benötigt, wird eine Antwort Message benutzt.


## Nachteile von synchroner Kommunikation
[[Synchrone Kommunikation]] wird oft verwendet, wenn eine gewisse Aktion ausgeführt werden soll und der Aufrufer direkt eine Rückmeldung benötigt.

=> Viele synchrone Aufrufe müssen nicht zwingend synchron sein und könnten auch asynchron ausgeführt werden.


- **Verfügbarkeit**: Wenn der Empfänger nicht verfügbar ist, schlägt der Aufruf fehl und der Fehler muss gehandhabt werden.
- **Fehlertoleranz:** Wenn ein Service crasht während einer Antwort läuft der Aufrufer in ein Timeout, welches auch gehandhabt werden muss.
- **Erweiterbarkeit**: Punkt zu Punkt Kommunikation führt zu einer höheren Kopplung und dadurch wird die Wartung teurer
- **Skalierbarkeit**: Bei Punkt zu Punkt Kommunikation ist das Load-balancing deutlich komplexer:
![[LoadBalancing1.png]]
Um die Last aufzuteilen, muss eine Zwischenschicht, der Loadbalancer, eingeführt und konfiguriert werden. Dies kostet meistens Geld, braucht Knowhow und ist eine weitere Fehlerquelle.

![[LoadBalancing2.png]]
Durch die Queue wird das Load Balancing automatisch übernommen.
Es werden zwar ein paar Container mehr benötigt, was aber sehr wenig kostet und es wird keine neue Technologie eingeführt.
