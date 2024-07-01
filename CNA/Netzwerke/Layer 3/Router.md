Der Router arbeitet auf dem [[Network-Layer]] und im Gegensatz zum einen [[Switch]] können hier [[Adressräume#IP-Adresse|globale Adressierung]] ([[IP-Adresse]]) gehandelt werden.
![[Router2.png]]

Der Router ist ein aktiver Teilnehmer in einem [[Netzwerke]] und kann somit auch direkt adressiert werden.

Der Router bestimmt über [[Routing-Algorithmen]] die günstigsten Pfade über eine Kette von Verbindungen zwischen Quelle und Ziel.
![[Router.png]]

# Unterschied zu [[Bridge]]
- Bridges sind effizienter bei Verbindungen mit wenigen Pfaden.
- Router sind effizienter in komplexen [[Netzwerke|Netzwerken]].
- Router werden über eine eigene [[Adressräume#MAC-Adressen|MAC-Adresse]] angesprochen und müssen somit nicht alle Pakete mitlesen.
- Router puffern ([[Store and Forward]]) alle Frames und interpretieren die logische Schicht-3-Adresse.
- Router machen eine aufwändige Wegsuche.