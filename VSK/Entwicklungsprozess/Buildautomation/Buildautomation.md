## Idee Mittels Skript
Man möchte ein Skript haben, welcher die notwendigen Tools um den [[Buildprozess]] auszuführen sequenziell mit allen notwendigen Parameter ausführt:

**Vorteile:**
- Vollautomatisiert.
- Reproduzierbare Ergebnisse.
- Lange Build können über Nacht laufen.
- Vollständige Unabhängigkeit von der Entwicklungsumgebung.

**Nachteile**
- Inflexibler Ablauf.
- Abhängigkeit von Shell und Plattform.
- Aufwendige Wartung und Erweiterung.

## Buildwerkzeug
Die Alternative zu einem einfachen Skript ist ein dediziertes [[Build-Werkzeug]].
Dieses ist optimiert für die Build-Aufgaben:
- Ausführen des [[Buildprozess]].
- Vereinfachter Umgang mit Ressourcen (Dateimengen)
- Abhängigkeiten überwachen und steuern.

Diese Tools sind in der Regel platformübergreifend.