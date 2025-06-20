Die Idee eines In-Memory-Datagrid ist die transparente Verteilung von Daten auf verschiedene Server.

**Eigenschaften**
- Applikationen skalieren
- Daten auf Clusternodes verteilen
- Daten Partitionieren
- Nachrichten senden und empfangen
- Parrallel Tasks verarbeiten
- etc.

**Beispiele**
- [[HazelCast]]
- Apache Ignite
- Oracle Coherence

## Bestandteile
- **Verarbeitungseinheiten**: Halten Teile der Daten im Hauptspeicher bereit.
- **Datenbank**: Speicher alle Daten dauerhaft.
- **Middleware**: Kommunikation zwischen Verarbeitungseinheiten.
![[InMemoryDataGrid.png]]

### Verarbeitungseinheit
- [[Topologie verteilter Systeme|Embedded-Topologie]]: Logik und Daten
- Daten liegen im RAM-Speicher der Cluster-Nodes.
	- Schneller als diskoptimierte Datenbanken.
	- verbesserte Reaktionszeit bei kritischen Anwendungen.

### Redundanz
- **Skalierbarkeit**: Last kann über verschiedene Cluster-Nodes verteilt werden.
- **Redundanz**: mehrere Kopien der Daten in verschiedenen Cluster-Nodes.
- **Elasizität**: Cluster-Nodes können im Betrieb hinzugefügt oder entfernt werden.

### Datenpartitionierun
Fixe Anzahl an Partitionen welche möglichst gleichmässig über das Cluster verteilt werden.
$$
\text{partitionId} = hash(keyData) \% \text{ PARTITION\_COUNT}
$$
Falls nun eine Node dazu kommt werden die 12 Partitionen auf alle Nodes wieder möglichst gleich verteilt.