- Optimierungsmodelle brauchen zu ihrer "Berechnung" ein/en Lösungsverfahren/-algorithmus ("Solver"), um eine optimale oder zumindest "gute" Lösung zu finden
- Oft ist der Lösungsraum unendlich oder endlich, aber zu gross, um alle zulässigen Lösungen zu erzeugen.
- **Prinzipiell schwierig, eine optimale Lösung zu finden**

## Exakt vs heuristisch
### Exakt
- Findet eine (global) optimale Lösung, oder
- Sagt zuverlässig aus, dass
	- Keine zulässige Lösung existiert, oder
	- Kein endliches Optimum existiert; Zielfunktion kann beliebig klein (bei Minimierungsproblem) gemacht werden

#### Enumerative Verfahren
- Explizite, vollständige Enumeration (= Aufzählung)
- Branch & Bound (oder search-infer-relax): "intelligentes" Absuchen des Lösungsraums – implizite Enumeration:
	- Branch (search): sukzessive Aufteilung des Lösungsraums.
	- Inferenz (infer): Verkleinern des Lösungsraumes durch (meist) logisches Schliessen
	- Bound (relax): optimistische Schätzungen des Optimalwertes zur Steuerung der Suche und zum Abbrechen der Suche in Teilen des Lösungsraums
#### Spezialisierte, Struktureigenschaften nutzende Verfahren
- Suche eingeschränkt im Lösungsraum
	- Beispiel: Beschränkung auf Extremalpunkte bei Minimierung einer konkaven Funktion über eine konvexe Menge
- Suche nach lokalen Kriterien
	- Beispiel: Abstiegsverfahren falls lokal optimal = global optimal
- Effiziente implizite Enumeration
	- Beispiel: So genannte dynamische Programmierung, auf Optimalitätsprinzip beruhend, z.B. für Problem des kürzestem Weges
- Gesteuerte Beschaffung lokaler Strukturinformation
	- Beispiel: Schnittebenenverfahren (Cutting Planes)
- Kombination von Verfahren aus a) und b)
	- Beispiel Branch & Cut: Kombination aus Branch & Bound und Schnittebenenverfahren

### Heuristisch
- Findet eine (hoffentlich) gute (evt. lokal opt.) Lösung, oder
- Sagt, dass es keine zulässige Lösung finden konnte
- Verpasst evtl. eine optimale Lösung oder erkennt nicht deren Optimalität
- Heuristiken sind oft auf einfachen, intuitiv plausiblen Regeln und Prozeduren aufgebaut

- Eröffnungsverfahren (konstruktive Verfahren)
	- Eine (hoffentlich) gute Lösung wird schrittweise aufgebaut
		- Beispiel: nach einem Greedy-Ansatz
- Verbesserungsverfahren ("local search")
	- Geht von einer (i.d.R.) zulässigen Lösung aus
	- Versucht sukzessive die jeweils vorhandene Lösung durch lokale Änderungen zu verbessern
		- Beispiel: 2-Austausch im Traveling Salesman Problem
- Eine Vielfalt dieser sog. "Meta-Heuristiken":
	- Abstiegsverfahren (simple descent, Terminologie für Minimierungsprob.)
	- Tabu Search
	- Simulated Annealing
	- Genetische Algorithmen