Wiederverwendung von bewährten [[Entwurfsmuster]] als Ziel.

Es gibt folgende Arten von Wiederverwendung in der Softwareentwicklung:
- Objekte zur Laufzeit wiederverwenden.
- Wiederverwendung von Quell-Code / Klassen
- Wiederverwendung von Komponenten
- Libraries
- Wiederverwendung von Konzepten.

**Herausforderungen** von Quellcode Wiederverwendung:
- Unterschiedliche Fachverständnisse / Kontext.
- Unterschiedliche Technologien.
- Einfache Weiterentwicklung / Wartung.
- Komplexes Konfigurationsmanagement.
- Inkonsistente Designprinzipien.
- Abhängigkeit von Lieferanten.

## Objektwiederverwendung
Bei der Objektwiederverwendung werden Objekte zur Laufzeit wiederverwendet:
- [[Thread|Threads]] in einem [[Threadpool]].
- Stringpool
- Integer-Cache
- Datenbankverbindungen

Dadurch wird die Perfromance verbessert, was zu einer höheren Effizienz und gerigngem Ressourcenbedarf führt.

**Herausforderungen**
- Effiziente Verwaltung der Objekte.

## Codewiederverwendung
Codewiederverwendung kann durch folgende Arten genutzt werden:
- Copy & Paste => schlecht (DRY)
- [[Vererbung]] => häufig Problematisch [[Liskov Substitution Principle]]
- Aggreattion und Komposition => gut ([[Item 18 Favor composition over inheritance]])

Durch die Codewiederverwendung wird der Entwicklungsaufwand reduziert und die Fehlerrate wird kleiner.

**Herausforderungen**
- Schnittstellen der Klassen eher fremdbestimmt.
- Auswahl von geeigneten Klasse / Bibliotheken
- Lernaufwand, Wartung und Weiterentwicklung

## Wiederverwendung von Kopmonenten
Beispiele für die Wiederverwendung von Komponenten sind:
- Logging (Log4j)
- EE-Beans
- Corba-Komponenten etc.

Durch die Wiederverwendung von Kopmonenten wird ein ganzheitlicher Ansatz nach dem Black-Box-Prinzip gefahren. Dies fürht zu einem geringerem Entwicklungsaufwand und weniger Fehler.

**Herausforderungen**
- Anforderungen an die Umgebung und Kontext
- Evt. inkompatible [[Schnittstelle|Schnittstellen]]
- Verwaltung von Komponenten.
- Abhängigkeit von Lieferant.
- Wartung und Weiterentwicklung

## Wiederverwendung von Konzepten
- Konzepte bleiben relativ konstant.
- Breit abgestützt, erprobt und bewährt.
- Implementations und Sprachunabhängig.
