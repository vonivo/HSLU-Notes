Ein [[Monolithische Architektur|Monolith]] ist auf einem hohen Abstraktionslevel einfach ein Haufen Methoden, welche sich gegenseitig aufrufen.

![[MSA1.png]]
Verwandeln wir jetzt diese Methoden in Microservices haben wir nun ein Micro-Service-Architektur.

![[MSA2.png]]

- Vorher haben Methoden andere Methoden im selben Adressraum aufgerufen. Nun werden die Methoden in **verschiedenen Adressräumen / Host** aufgerufen.
	- Latenzzeit steigt von Nanosekunden zu Mikrosekunden/Millisekunden
- Da die Methoden nicht mehr im selben Adressraum sind, muss jetzt **Serialisierung** benutzt werden.
- Daten werden meist Binär serialisiert. (XML & JSON ~10-20x grösser)

## Microservice
>[!Error]
>Es ist wichtig keine "verteilten Monolith" zu bauen. Das System soll überdenkt werden und service-orientiert wiederaufgebaut werden.

**Eigenschaften**
- Ein MS besitzt eine Art **Interface**
- Ein MS besitzt eigene **Businesslogik**
- Ein MS besitzt eigene **Daten**

