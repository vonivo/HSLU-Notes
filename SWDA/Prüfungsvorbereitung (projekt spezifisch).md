
# Context-Diagram
- menschliche Akteure -> Datentypist, Sysadmin, Filialleiter und Verkäufer
- externe Systeme -> Buchhaltungssystem, Zentrallager

# Domain-Model
## Order-Context
### Invoice
- Enthält Zusätzlich zur Order nur den Status und Summe.
- Könnte rein Theoretisch auch weggelassen werden
	- Beide zusätzlichen Attribute würden auf Order verschoben werden
	- Handling von Invoice wird komplett von externem Service gehandelt
		- Eventuell könnte man dann sogar den Status komplett weggelassen.
#### Beziehungen
- Zu Order eine `0..1 - 1` Beziehung.
	- Zu jeder Invoice existiert genaue eine Order.
	- Eine Invoice wird erst erstellt, wenn die Order nicht mehr verändert wird -> daher `0..1`

### Order
- Enthält Id, dateCreate und Status (für State-Machine)

#### Beziehungen
- Zu OrderPosition mit `0..n - 1`.
	- Jede OrderPosition gehört genau zu einer Order
	- Jede Order kann 0 oder mehrere OrderPositions enthalten.
		- Rein logisch wäre es eine `1..n - 1` Beziehung ist jedoch unnötig limitierend. (Beispiel mit aufgetrennten Ressourcen für Order und OrderPosition)
- Zu Customer mit `0..n - 1`
	- Keine Bestellungen ohne Customer erlaubt -> nimmt Komplexität.
	- Anonyme Bestellung über "anonymousCustomer" möglich -> Ähnlich zu Special-Case-Pattern.
	- *Unidirektional* -> User kennt Orders nicht direkt
- Zu User mit `1 - 0..n`
	- Jede Bestellung muss von einem Verkäufer erstellt worden sein, da Anwendung nicht direkt vom Kunden genutzt wird.
	- Könnte einfach auf verhältnismässig einfach auf `0..n - 0..1` relaxiert werden.
	- *Unidirektional* -> User kennt Orders nicht direkt
- Zu Reservation `0..n - 1`
	- Eine Order kann Reservations im Inventory-Context triggern muss jedoch nicht.
	- *Unidirektional* -> Orders kennen zugehörige Reservations nicht
- Zu Store `0..n - 1`
	- Jede Order wird genau aus einem Store verkauft.
	- Multitennant-Fähigkeit
	- *Unidirektional* -> Store kennt Order nicht

### Order Position
- Id, ArticleNumber, quantity, Price
- **Fehler im Diagramm:** Price nicht abgebildet.
- Bewusste Redundanz des Price. -> Einerseits sollten keine Komplexen-Relations (direkt über Objekte) über Context-Grenezen hinaus entstehen aber vor allem wichtig weil Oder-Daten nicht verändert werden sollen wenn sich der Preis eines Artikels ändert.

### Beziehungen
- Mit Article `0..n - 1` Jede OrderPosition hat genau einen Artikel. Ein Artikel kann x-Fach gekauft werden oder nie.
- *Unidirektional* -> Artikel kenne OrderPosition nicht

## User Context
### User
- Id, Username, Password, Firstname, Lastname
- Könnte definitiv noch mit weiteren Felder ergänzt werden falls nötig.

#### Beziehungen
- Mit Store `1 - 0..n`
	- Jeder Store kann 0 bis x Benutzer haben, jeder Benutzer existiert aber genau in einem Store.

	- Entscheid, dass User (also Systembenutzer) an einen Store gebunden sind. Annahme, dass Stores sehr unabhängig untereinander sind.
	- Einfaches handling des Multitennants -> StoreId kann in JWT rein und dadurch einfach abfragbar
	- Datensicherheit und visibility kann besser eingeschränkt werden
	- Eventuell könnte auf  `m - n` erweitert werden, wenn Sonderfälle auftreten würden -> **Wäre besser gewesen** (dann müsste jedoch Current-Store beim Login durchgereicht werden)
- mit Rolle `0..n - 0..n`
	- Aus Aufgabenstellung hätte `0..n - 1` gereicht -> weniger flexibel
	- *Unidirektional* -> Rollen kennen Benutzer nicht
- mit Refreshtoken `0..n - 1`
	- Nur gespeichert da invalidierung.
### Rolle
- Id, Role
- Bisher noch keine Vererbung vorgesehen -> wäre einfach erweiterbar.
	- Änderung würde sich auf UserService beschränken
### RfreshToken
- Id,refreshToken,revoked,dateCreated
- Wird nur abgespeichert, dass beim einem "Master-Logout" (existiert noch nicht) auch alle Refreshtokens revoked werden können. 

## Customer-Context
- Id,Firstname,Lastname,Address,email
- Eigener Context -> biser noch sehr schmal -> Könnte aber durchaus kompliziertwer werden -> z.B. Rabatte -> Business-Partner -> etc.
- Adresse nicht sauber normalisiert (KISS für Schulprojekt)

## Inventory-Context
### Article
- ArticleNumber, name, price

- Repräsentiert Artikel im Zentrallager

#### Beziehungen
- Mit Stock `0..n - 1`
	- Jeder Stock hat genau einen Artikel
	- Ein Artikel kann in 0 oder mehreren Filianen als Stock geführt werden

### Stock
- Id, minimumQuantity,qunatity

- Räpresentiert den Lagerbestand von einem Artikel in einer Filiale.

#### Beziehungen
- Mit RestockOrder `0..n - 1`
	- Zu einem Stock kann es 0 oder n RestockOrders geben.
	- Jede RestockOrder gehöhrt aber genau zu einem Stock.
- Mit Reservation `0..n - 1`
	- Es kann zu jedem Stock 0 oder n Reservations geben
	- Jede Reservation behandelt genau einen Stock
- Mit Store `0..n - 1`
	- Jeder Stock gehört genau zu einem Store
	- Jeder Store kann beliebig viele Stocks enthalten.


### RestockOrder
- Id,dateCreated,qunatity,status,deliverableFromCentralStockAt

- Räpresentiert eine Nachbestellung eines spezifischen Artikels von einer Filiale


### Reservation
- Id,orderId,orderedQunantity,reservedQuantity

- Bewusste Redunandz der orderedQunantity (währe in der Order ersichtlich) -> Inventory-Context wird dadurch unabhängiger und Weniger Strukturelle sowie Laufzeitkopplung
- Repräsentiert die Reservation von einer bestimmten Quantität für eine Bestellung.
- **Könnte**, wenn order fertig kommissioniert wurde gelöscht werden -> wurde noch nicht implementiert. Kein zeitlicher Druck -> könnte auch asynchron über einen Background-Job gemacht werden.

### Store
- id, name

- Repräsentiert eine Filiale.

# BPMN
## Fehler
1. Kunden erfasst sein bevor die Bestellung angelegt werden kann
   Erste Parallelisierung kann nicht gemacht werden.
2. Preisabfrage nicht eingetragen (Weiss nicht ob zwingend -> da es keine Businesskation an sich ist.)
3. "Artikel abbuchen" und "Bereits vorhandene Artikel reservieren" ist an sich die gleiche Aktion im Code -> ist jedoch besser für die Verständlichkeit dies so im Prozess zu lassen (Kann auch als Fehler oder Faulheit gewertet werden)

## Potenzial
1. Artikelprüfung könnte auch bei Nachricht "Lagerbestand verändert" getriggert werden --> effizienter

# Microservice Modell
## Fehler
- Bewusster Verzicht auf gewisse Methoden welche das Diagramm unübersichtlich machen (auch die Preisabfrage -> "nur" Validierung und nicht expliziter Prossschritt wie Mahnungsprüfung)

## Verbesserungen
### Kommissionierung von einzelnen OrderPositions
Momentan wird immer eine Order als ganzes kommissioniert, dies hätte auch anders Realisiert werden können, indem einzelne OrderPositions kommissioniert worden wären.

#### Nötige Änderungen
- Reservation-Entry speichert OrderPositionId anstatt OrderId
- Umbennen der Schnittstelle `orders.commission` und `ordres.commissioned` zu `order.orderPosition.commission` und `order.orderPosition.commissionEnd`
- Anpassung der Kommissionierungslogik
	- Nur noch eine einzelne OrderPosition wird kommissioniert
	- Check ob Order Vollstädnig kommissioniert wurde wird in OrderService verschoben.

#### Auswirkungen
1. OrderService wird komplexer und muss "Order-Completion" handeln
2. Invetory-Service wird weniger komplex -> logik wird verschoben
3. Strukturelle Kopplung bleibt gleich (immer noch 2 Schnittstellen)
4. Semantische Kopplung steigt -> OrderService mehr auf InventoryService angewiesen
5. Laufzeitkopplung wird erhöht -> mehr Messages
6. Fachliche Resilienz wird gestärkt -> granularere Messages und granularere Fehlerscopes -> kein künstliches kummulieren von potentiziellen Fehler
7. Fehlertoleranz gegen Infrastrukturausfälle nimmt ab.
8. Fachlicher Ablauf wird komplexer -> Logik wird verteilt -> keine Balckbox mehr
9. Netzwerklast wird minimal erhöht
10. Bessere Skalierung da mehr Events welche asynchron verarbeitet werden können.
11. Bessere Erweiterbarkeit

#### Variante Alt
- Order atomar
- Einfach
- verständlich
- robust

**Variante Neu**
- Fachlich Robuster
- OrderPosition wird atomar
- OrderPosition-Statemaching nötig
- Bessere Skalierung

### Aufsplitten von Inventory-Service
-  "PIM"-Service für Produkt-Informations-Management.  Zu diesem Bounded-Context würde bisher "nur" der Artikel gehören, könnte dann aber auch  mit Produkt-Features, verschiedenen Klassifikationskatalogen, etc erweitert werden.
   Würde gut passen, da Artikel recht "unabhängig" ist.
   
   -> An sich keine Veränderung des OrderService und nur Inventory-Service betroffen.
   -> Wäre auch eine gute Separierung wenn noch weitere Funktionalität wie z.B. Produkt-Vergleich gewünscht wird.

- Auslagerung von Restock-Order wäre ebenfalls möglich, da recht unabhängig.
  
  Falls ein komplexer Prozess mit evt. Qualitätssicherung bei Restock gefordert ist, könnte das noch Sinn machen.
  
  -> **Achtung:** Würde dann eine Saga oder andere Konsistenzmechanismen benötigen, da Restock und Stock zusammengehören. -> Eventuell ein eigener Bounded-Context oder zwei Services für einen Bounded-Context.

- Wenn komplizierte Pricing-Strategie -> eigener Pricing Service
	- Hat Hoheit über Preise (keine Preise im PIM und Inventory)
	- Kennt komplexe Rabattlogiken
	- Berechnet den vollen Preis einer kompletten Order
	- **Achtung:** Bisheriger "Validierungsflow" müsst erweitert werden, da PRICED nicht mehr "OrderPositions-Valid" entspricht. -> Order-Statemachine würde erweiter werden.

- Falls Nötig könnte auch Store ein eigener Bounded-Context werden


# Events & Endpoints
## Gateway
- Nicht ganz REST konform
- REST Level 2 (kein Hypermedia-Controls und bisher nur eine Darstellung)
- restockAssortmentItem -> **Aktionsorientiert**
- deliver -> **Aktionsorientiert**
- approve -> **Aktionsorientiert**

## Events
- `orders.cancel` -> könnte man auf `reservations.free/delete/cancle` ändern. Etwas aussagekräftig, weil `orders.delte` bereits existiert. Eventuell wäre `orders.decommission` nicht schlecht

- Bessere Aufteilung in Commands & Events
	- z.B. `orders.delte` von Gateway an OrderService. Daraus folgt dann `orders.deleted`
- Queries (abfragen vom Gateway) aus Liste entfernen, übersichtlicher

# Component Diagramm
- Architektornische Unschönheit:
	- Service-Klassen arbeiten teilweise direkt mit DTOs
	- Service-Klassen rufen direkt Clients aufs
	- Keine Modelklassen (aber i.O. wegen YAGNI)
	Wiederspricht dem Layering mit der Busniesslogik in der Mitte und das I/O (Listener, DB, Clients) rundherum.
	-> Lösbar eventuell über Callback
	-> Modell->Mapping (Achtung: Wird es wirklich benötigt.)

# State-Machine
- Unnötige Wartezeit durch "synchronisierung" von Preisabfrage und Mahnungsprüfung
- Verbesserungsvorschlag -> einzelner State "WAITING" welcher wiederum eigene State-Flags (priced, dunning, etc.) mit sich führt.
- So in etwa State-Machine in State-Machine
- Vorteil: **Parallelität**
