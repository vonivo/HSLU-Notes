Das Internet ist eine Ansammlung von [[Netzwerke|Teilnetzen]], welche hierarchisch aufgebaut sind.
![[Backbone.png]]
Der hierarchische Aufbau dieser Nezte wird von den Unternehmungen **IANA** und **ICANN** gemacht. Ohne diesen Aufbau wäre das Routing fast unmöglich.

Damit das Routing funktioniert, muss das Teilnetz in einen [[AD/Algorithmen/Graphen/Graph]] umgewandelt werden:
![[Routing_1.png]]
- Jeder Router kann auf jeden Router zugreiffen, der am gleichen Teilnetz angeschlossen ist.

Danach erfolgen die Routing-Algorithmen.

# Statisches Routing
Beim Statischen Routing wird beim Konfigurieren des [[CNA/Netzwerke/Layer 3/Router|Router]] die Routing-Tabelle fix erstellt, welche sich dann auch nicht mehr ändernt.

Dementsprechend ist das statische Routing "einfacher" da es keine Anpassungen mehr gibt.

# Dynamisches Routing
Beim dynamischen Routing werden die Routing-Tabellen der Router zur Laufzeit angepasst und verändert.
Dadruch werden zusätzliche Protokollmeldungen während des Betriebs erforderlich.

Dynamisches Routing kann jedoch mit Fehlern innerhalb des Netzwerks umgehen.

## Shortest Path Algorithm
Bie diesem Algorithmus wird der [[Algorithmus von Dijkstra]] angewendet, um den kürzesten Weg vom Start zum Zielrouter zu berechnen.

## Flooding
Beim Flooding-Algorithmus wird jedes Paket über alle Ausgangsleitungen als Broadcast gesendet -> Fluten des Netzes.

Die Flut wird mittels TTL kontrolliert und sobald ein Paket beim Empfänger angekommen ist, ist der schnellste Pfad gefunden.

-> Aufwändig und statisch
-> Robustes ergebnis
-> Dient meist als Benchmark für andere Algorithmen

## Distance Vector Routing
Dieses Routingverfahren ist dynamisch und berücksichtigt zusätzlich noch die Netzlast.

Jeder Router besitzt eine Tabelle mit den bestmöglichen Verbindungen wobei sich benachbarte Router austauschen.

-> Informationen über schlechte Kanäle verbreiten sich langsam.

## Link State Routing
Jeder Router ermittelt immer seine Nachbarrouter und die Entfernung zu diesen.

Diese Informationen werden im gesamten Netz verbreitet, so wird die gesamte [[Netzwerktopologien|Topologie]] erforscht.

Im Anschluss Berechnung mit dem [[Algorithmus von Dijkstra]].


# OSPF
Der [[Algorithmus von Dijkstra]](SPF) ist der reine Algorithmus, mit welchem der Pfad bestimmt wird.

OSPF (Open Shortest Path First) ist ein Protokoll, welches durch Link State-Routing den Graf des Netzwerks bestimmt, um danach mit SPF den Weg zu bestimmen.

# Spezielle Routing Algorithmen
**Hierarchisches Routing**
- Router in Regionen eingeteilt (Internet mit ICANN / IANA).
- Jeder Router kennt sich nur in seiner Region aus.
- Nur "überregionale" Pakete werden über Verbindungsrouter in andere Regionen geschickt.
- Mehrstufige Hierarchie, z.B. Regionen, Cluster, Zonen, Gruppen

**Broadcast-Routing**
- Versand einer Nachricht an alle Hosts (eines Teilnetzes)
- Methoden: Multidestination-Routing, [[AD/Algorithmen/Graphen/Graph#Spanning Tree|Spanning Tree]]

**Multicast-Routing**
- Versand an eine Gruppe von Hosts.
- Router muss wissen, welche Hosts zu welcher Gruppe gehören.
- Router berechnet Spanning-Tree

**Routing für mbile Hosts**
- z.B. Mobile-IP (Stationen die sich bewegen. IPv4 -> schwierig, IPv6 -> einfacher)

**Routing in Ad-Hoc-Netzen**
- Keine feste Topologie, Hosts werden spontan (ad-hoc) vernetzt.
- IOT-Schwärme, Automobilnetze, Notfallnetze.
