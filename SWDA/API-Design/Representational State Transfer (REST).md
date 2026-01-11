---
aliases:
  - REST
---
REST ist ein **Architekturstil** und definiert einen Satz von Prinzipien, welche eine REST-konforme Architektur einhalten soll:
1. **Stateless** Kommunikation
2. Verwendeung von (http(s)-)**Standardmethoden**
3. **Ressourcen** mit eindeutiger Identifikation (URI)
4. Unterschiedliche **Repräsentation** von Ressourcen
5. **Verknüpfungen** / Hypermedia (HATEOAS)

>[!info]
>Eine REST-konforme Architektur basiert zwangsläufig auf einer verteilten Client/Server Architektur, meist mit http(s)-Protokollen.


## Zustandslosigkeit
Die Kommunikation **muss** bei REST zustandslos sein. Es existiert keine Session auf dem Server!

Der Zustand muss entweder vom Client gehalten, oder (**besser**) vom Server einer Veränderter Ressource abgebildet werden.

Der Zustand der Applikation ergibt sich ausschliesslich aus der Ressourcerepresäntation (URI) und dem Ressourcenstatus.
- Keine Sitzungsinformationen.

-> Bessere horizontale Skalierbarkeit
-> Setzen von Bookmarks problemlos möglich

## Standardmethoden
Eine REST-konforme Applikation verwendet die http-Methoden `GET`, `PUT`, `PATCH`, `POST`, `DELETE` etc. in verbindlicher Weise
![[REST.png]]
- `GET`, `PUT`, `PATCH` und `DELETE` können beliebig oft aufgerufen werden -> **ohne Seiteneffekte**.
- Die Methode `POST` darf nicht mehrfach aufgerufen werden, da sie Seiteneffekte hervorrufen kann -> **Nicht idempotent**

## Identifizierung von Ressourcen
Ein Ressource ist eine Informationseinheit welche über eine URI eindeutig identifiziert werden kann.

Die Ressource kann jedes beliebige Datenformat nutzen:
- Meistens JSON oder XML
- Ideal wenn die Repräsentation über `Accept: MIME-Type` gewählt werden kann.

>[!error]
>Ein REST-konformer URI enthält keine Namen von Operationen!

### Namensgebung
URIs für REST-Schnittstellen folgen strikten Konventionen:
- Bezeichner werden typisch in **Mehrzahl** geschrieben
- IDs (Schlüssel) sind immer Bestandteil des Pfades
	- Nie als Attribute übermitteln
- Nur für Suchargumente dürfen zusätzliche Attribute verwendet werden

=> Mit ein und derselben URL kann man basierend auf der HTTP-Methode nun unterschiedliche Aktionen ausführen.

### Rückgabewerte über Body und Statuscode
Bei RESTfull-Schnittstellen über http sind wir in der «komfortablen» Situation, dass wir «mehrere» Rückgabemöglichkeiten haben:
- Über den Content/Payload (Body) des Request.
- Andererseits über den http-Statuscode

Auch hier sollte eine klare Zuordnung gemacht werden:
![[REST2.png]]
## Hyermedia-Prinzip
Dieses Konzept ist dafür da unterschiedliche Ressourcen über Links miteinander zu verknüpfen.

Der Client kann über eine Antwort den enthaltenen Verknüpfungen dynamisch folgen.

```xml
<bestellung href='http://fbs.hslu.ch/bestellungen/73'>
	<datum>2017-12-18</datum>
	<betrag>1694.65</betrag>
	<produkt href='http://fbs.hslu.ch/produkte/53' />
	<kunde href='http://fbs.hslu.ch/kunden/421' />
</bestellung>
```


# RESTfull - Richardson Maturity Mode (RMM)
Eine Applikation ist (erst) dann wirklich «RESTfull», wenn die wesentlichen REST-
Prinzipien eingehalten werden.

Zur Beurteilung kann das Richardson Maturity Model (RMM) herangezogen werden:
![[RESTfull.png]]
- Es werden keine festen Ressourcennamen oder Hierarchien vorausgesetz: Der Server soll die Struktur der URIs jederzeit ändern können, **ohne** dass der Client angepasst werden muss. 
Um dies zu erreichen braucht der Client nur die "**Einsteigs-URL**" -> Alle weiteren URLs sind durch HATEOAS vom Server übermittelt worden.

- Keine Abhängigkeit von einem spezifischen Kommunikations-protokoll: Die Anwendung muss mit http-URIs, ftp-URIs und auch mit file-URIs funktionieren

- Die bereits definierten Protokolle dürfen nicht geändert werden (GET bleibt GET, PUT bleibt PUT etc)


## Versionisierung
Im Vergleich zu anderen (class-based) Schnittstellen, können REST-Schnittstellen über einen URI-Pfadanteil relativ einfach versioniert werden.
- Paralleler Betrieb problemlos möglich.
```
http://fbs.hslu.ch/api/v1/orders - Version 1 der Schnittstelle.
http://fbs.hslu.ch/api/v2/orders - Version 2 der Schnittstelle.
```

Wenn möglich ersetzt man die alten Versionen jeweils durch eine Wrapper-
Implementation (Translator) auf die neuste Version!
- So vermeidet man Coderedundanzen und erhöhten Wartungsaufwand, und hat trotzdem einen «zentralen» Zugriffspunkt.