Ein [[VSK/Deployment/Deployment|Deployment]] findet immer in einem definierten Relases statt.
Dieser Release hat:
- Eindeutige Bezeichnung und Version.
	- Technische Version ist die eindeutige Identifikation ([[Semantic Versioning]])
	- Tagging im [[Versionskontrollsysteme|VCS]]
	- Marketing-Version unbedingt trennen, als Ergänzung.


## Alternative Versionierung
### Time Based Release Versioning
Es existiert ein fester Release Zyklus / Takt an Release-Terminen.

Versionsnummer macht deutlich, um welchen Zeitpunkt es sich handelt.
**Beispiel**: 23.09, 24.04, 24.09, etc.

Macht Sinn bei grossen Produkten und/oder Marketing-Versionen.
Bei Libraries/Komponenten eher nicht sinnvoll.

**Beispiel Java**
Versionen in Java haben seit 2017 folgendes Format:
```
$FEATURE.$INTERIM.$UPDATE.$PATCH
```
- **Feature**: Inkrementeller Counter, aktuell bei `21`
- **Interim**: Bleibt derzeit bei `0`
- **Update**: Inkrementeller Counter für Updates, derzeit bei `3`
- **Patch**: Optionale Patch-Nummer

Feature-Releases werden alle 6 Monate (jeweils März und September) fällig.
Update gibt es meistens 1 und 3 Monate Später.

Alle 2-3 Jahre wird eine Version als LTS publiziert.

