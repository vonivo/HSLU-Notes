>[!info]
>Eine Datenstruktur ist ein **Konzept zur Speicherung und Organisation von Daten**.
>Die Struktur gibt vor, auf welche Art und Weise die Daten gespeichert werden, wie darauf zugegriffen wird.
>
>-> Werden durch Operationen charakterisiert.

Datenstrukturen bedingen meist spezifische [[Algorithmus|Algorithmen]].

## Eigenschaften
- **Reihenfolge / Sortierung**: In welcher Reihenfolge werdend die Elemente abgelegt.
	- Reine Sammlung und ungeordnet? (Analogie Steinhaufen)
	- Bestimmte Reihenfolge einhalten (z. B. Einfüge Reihenfolge) -> Stapel
	- Sortierung, werden die Daten beim Einfügen sortiert gespeichert (Hochregallager)
	
- **Operationen**: Welche Operationen stehen zur Verfügung
	Elementare [[Methode|Methoden]] die auf der Datenstruktur angewendet werden können?
	- Einfügen
	- Suchen
	- Entfernen
	- Ersetzen
	
- **Statische oder dynamische Datenstruktur**: Kann die Datenstruktur ihre Grösse dynamisch verändern oder ist sie statisch.
	**Statische** Datenstrukturen haben nach Initialisierung immer die gleiche unveränderliche Grösse und kann somit eine bestimmte Anzahl Elemente aufnehmen.
	- Datenstruktur benötigt immer gleich viel Speicher.
	- Datenstruktur hat bestimmte Anzahl an Platz.
	**Dynamische** Datenstrukturen kann Grösse während der Lebensdauer verändern und eine beliebige Anzahl Daten aufnehmen.
	- In leerem Zustand wird fast kein Speicher benötigt.
	- Speicherbedarf wächst mit Anzahl der Daten.
	
- **Explizite oder implizite Beziehungen**: Bestehen zwischen den Elementen explizite oder implizite Beziehungen.
	**Explizite** Datenstrukturen werden Beziehungen von Daten explizit mit Referenzen festgehalten. (Fahrradkette).
	- Jedes Element kennt sein zwei Nachbarn.
	**Implizite** Datenstrukturen halten die Beziehung zwischen Daten implizit fest.
	- Beziehung wird quasi von aussen definiert (z.B. über eine Nummerierung).
	- Analogie Buchregal mit Büchern
		- Bücher stehen eifnfach nebeneinander
		- Buch selber weiss nicht wo es in der Reihe steht.
	
- **Zugriffsmöglichkeiten**: Besteht direkter oder nur indirekter Zugriff auf die einzelnen Daten.
	**Direkter** Zugriff ist, wenn jedes Element direkt einzeln angesprochen werden kann. (Bücherregal -> jedes Buch kann einfach herausgenommen werden).
	**Indirekter** Zugriff ist, wenn man nicht einfach ein Element ansprechen kann, sondern sich  z.B. sequenziell durcharbeiten muss bis das Element gefunden wurde.
	- Tellerstapel -> Wenn ein spezifischer Teller gewählt wird, muss man alle Teller oberhalb zuerst entfernen
	
- **Aufwand der Operationen**: Wie gross ist der Aufwand für die einzelnen Operationen, speziell in Abhängigkeit zur Datenmenge.
	- Aufwand variiert für verschiedene Operationen als auch in Abhängigkeit der Datenmenge und Datenstruktur.
	- Meistens interessiert nur die [[Komplexität|Ordnung]]
