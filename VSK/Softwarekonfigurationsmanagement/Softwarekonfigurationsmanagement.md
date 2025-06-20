>[!Definition]
>Ziel des **Softwarekonfigurationsmanagements** ist, Änderungen von Konfigurationen über gesamten Systemlebenszyklus kontrolliert unter Einhaltung von Integrität und Rückverfolgbarkeit durchführen.

**Methodik**
Identifikation der Konfiguration eines Systems
- auf verschiedenen Ebenen
- zu verschiedenen, definierten Zeitpunkte


Während der Entwicklung und im Betrieb eines Systems sind **Bestandteile** Änderungen unterworfen. Dazu gehören:
- Software
- Hardware
- Konfigurationen (Einstellungen)
- Firmware
- Dokumentation

Nicht alle Versionen aller Bestandteile sind miteinander kompatibel. Softwarekonfigurationsmanagement stellt diese Kompatibilität sicher.


## Begriffe
**Konfiguration**
Sammlung bestimmter Versionen von Bestandteilen einer Software, welche gemäss einem festgelegten Verfahren kombiniert werden, um einen bestimmten Zweck zu erreichen.

**Konfigurationselement** 
Aggregation von Software, welche im Rahmen des Konfigurationsmanagements, als _einzelne Einheit_ behandelt wird.z.B.:
- Pläne
- Spezifikationen
- Bibliotheken
- Daten und Verzeichnisse
- Dokumentation für Installation, Wartung und Betrieb

**Version** 
Spezifisches, identifizierbares Artefakt eines Konfigurationselements auf einem bestimmten Entwicklungsstand.

**Revision** 
Neue Version eines Artefakts mit dem Zweck, eine ältere abzulösen.

**Baseline**
Ein Satz von Revisionen, d.h. ein Snapshot der Konfiguration

**Release:**
Eine getestete und freigegebene Baseline