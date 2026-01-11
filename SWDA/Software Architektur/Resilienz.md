Begriff stammt ursprünglich aus der Psychologie und beschreibt die psychische Widerstandsfähigkeit, um z.B. Krisen zu bewältigen.

>[!Definition]
>Die Fähigkeit von technischen Systemen, bei Störungen bzw. Teilausfällen nicht vollständig zu versagen, sondern wesentliche Systemdienstleistungen aufrechtzuerhalten.

Auf [[Microservice|Microservices]] bezogen: Eine Applikation sollte weiter (eingeschränkt) funktionieren können, wenn gewisse Microservices nicht verfügbar sind.


## Ausfall eines [[Microservice|Microservices]]
Wenn ein Microservice nicht verfügbar ist, existieren im Groben diese zwei Szenarien:

1. Ein Service ist komplett **nicht verfügbar** oder wird nicht gefunden.
    - Verbindung kann nicht aufgebaut werden, Fehlersituation wird vom Aufrufer relative schnell erkannt -> Abbruch, klare Situation.
2. Ein Service arbeitet **sehr langsam**: Antwortzeit erhöht sich stetig (z.B. Ressourcenprobleme).
	-  Verbindung kann aufgebaut werden, Aufrufer ist wesentlich länger blockiert (nur bei [[Synchrone Kommunikation]]), läuft aber (noch) in ein Timeout.
=> [[Circuit-breaker]]
