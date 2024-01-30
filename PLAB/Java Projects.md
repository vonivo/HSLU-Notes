
## Projekt Valhalla
Soll die Unschönheit zwischen primitiven Datentypen und Objekte glätten.
Dabei soll es in Zukunft möglich sein, eine `new ArrayList<int>()` zu erstellen.

Dafür sollen zwei neue Arten von [[Klasse|Klassen]] eingeführt werden:
**Value-Class**:
- Felder sind implizit final ([[Immutable Objects]]) -> keine Identität mehr.
- Besitzen jedoch eine Objektreferenz

**Primitive Class**:
- Keine Identität
- Keine Referenz
- Mehr Performance Verbesserung möglich (vom Compiler)

=> Noch keine Preview in Java 21.


## Projekt Panama
Wird Interaktionen mit anderen APIs vereinfachen.

- Vector API
	- Vector-Instructions auf supporteten CPU-Architekturen ausführen
	- -> **Incubator**
- Foreign Function and Memory API
	- Erlaubt es auf Code und Daten außerhalb der Java Runtime zuzugreifen
	- Ersetzt Java Native Interface
	- **Preview in 21, Feature in 22**
- JExtract
	- Tool um Java Bindings von native library headers zu erstellen.

## Projekt Loom
Verbessert die Concurrency in Java mittels "Virtual Threads"

- Virtual Threads -> **in Java 21**
	- Sehr "leichte" Threads welche von der JVM gesteuert werden.
- Structured Concurrency
	- **Incubator**


## Projekt Amber
Ziel ist es Java im allgemeinen produktiver zu machen über teils kleinere Verbesserungen oder aber auch grössere.

- Lokale Variable Typinterferenz (var) -> **in Java 10**
- Java Text-Blocks -> **seit Java 15**
- Records -> seit **seit Java 16**
- Patternmatching
- Sealed-Class **seit Java 17**
- Switch-Verbesserung

Stetig in Verbesserung und im Release (Bsp. String-Templates, unnamed variables, etc)