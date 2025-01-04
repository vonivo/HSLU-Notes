Die Paketvermittlung, die zentrale Aufgabe des [[Network-Layer]]. Sie bestimmt, welchen Weg ein Paket einschlägt um beim Ziel anzukommen.
# [[Verbindungslose und verbindungsorientierte Dienste#Verbindungslos|Verbindungslos]]
- Jedes Paket wird einzeln verschickt.
- Paket wird auch Datagramm genannt.
- Dei [[CNA/Netzwerke/Layer 3/Router|Router]] geben das Paket jeweils an den nächsten [[CNA/Netzwerke/Layer 3/Router|Router]] weiter.
- Die Auswahl des nächsten Routers erfolgt dynamisch aufgrund der Paketadresse.

## Beispiel
1. PC H1 sendet insgesamt 4 Pakete dem PC H2.
2. PC H1 sendet die Packete dem Router A.
3. Router A sendet die Pakete gemäss seiner Routing Tabelle weiter:
![[Routing-Table.png]]
4. Jeder Router hat eine eigene Routing-Tabelle und sendet die Pakete dementsprechend weiter.
5. Nach dem 3. Paket steigt Router C aus -> Routing-Tabellen werden angepasst.
6. Paket 4 nimmt einen anderen Weg.
![[Datagramm_routing.png]]

# [[Verbindungslose und verbindungsorientierte Dienste#Verbindungsorientiert|Verbindungsorientiert]]
- Pakete werde einzeln ans Netz übergeben.
- Für die gesamte Übermittlung wird eine **virtuelle Verbindung** eingerichtet.
- Jedes Paket besitzt ein Kennzeichen, welcher Verbindung es angehört.
- Die Router geben das Paket immer auf demselben Weg weiter.

## Beispiel
1. Der PC H1 möchte ien Nachricht an H2 senden -> H1 fordert Verbindungsaufbau an.
2. Aufbau der virtuellen Verbindung (VC, Virtual Cricuit) -> In jedem beteiligten Router werden entsprechende Einträge in die Routing-Tabelle gemacht.
	- Tabelle gibt jeweils an: Quelle:Verbindungs# | Ziel:Verbindungs#
	- Die Verbindungs# ist immer lokal zwischen zwei Routern.
4. H1 sendet Paket an A.
5. Jeder Router gibt das Paket gemäss Routing-Tabelle weiter.
6. Nach der Übertragung wird die Tabelle wieder gelöscht.

![[Verbindungsorientiertes_routing.png]]