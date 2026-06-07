- Feedback-based development & continuous delivery
	- Immer neue Anforderungen -> Ändern potentiell die Grundstruktur --> Lösung: Eveolutionary-Architecture
		- Sackgassen vermeiden

Prinzipien:
- Kurzfristig Handeln
- Langfristig Decken (Sackgassen vermeiden)
- **Beispiel:**
	- Skalierung: nicht am Anfang schon einbrigen, wird aber am schluss zu Thema

**Beispiel CaliTime**
1. Daten nur im Memory (für Demo-Version)
2. Persistenz komplett abstrahieren (Späterer Wechsel auf RDBMS o.Ä. ermöglichen)
3. DBMS Technologie wählen (Schon fast das ganze Schema und Anfroderungen klar)
4. Erweiterung mit anderen Speichertechnologien für spezifische Use-Cases
	1. Document-Based
	2. Key-Value
	3. Graph-Based
5. Scaling
	1. Mit Azure-SQL (auto-scaling)

## Enablers
- Software sollte möglichst einfach und verständlich sein
- Entscheidungen aufteilen und wenn möglich verzögern (Alle Optionen offenhalten)
	- Lösung in Schritten bauen
	- Möglichst pro Schritt Feedback einholen
- Architektur-Refactoring
	- Anpassen
	- Möglichkeit zur Reaktion schaffen

## Users Mental Code
- Jeder User hat ein mentales Modell wie der Code (Funktionalität) zu funktionieren hat
- Software sollte möglichst nahe an diesem Modell sein

- Beispiel: Email, Letter und Document mit `TextDocumentHolder`

# Behaviour vs. Entities
Buch:
	- Titel
	- ISBN
	- Author
	- etc.
- Nicht als Entity sonder als Objekt
	- `create(title, author, isbn)`
	- `correct(title)
	- `addRating(rating)`
	- `setPrice(price)`

- Hardcoding tielweise einfacher und felxiblre als Konfigurierbar und kompliziert
- Funktionalität sollte einfach "entfernbar" sein.
	- Bounded Contexts
- Orchestrator welcher Komplexität in die Breite verteilt -> einfacher austauschbar
- 