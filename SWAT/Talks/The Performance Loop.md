Benchmarking:
- Beispiele sehr einfach -> Prouktion komplett anders
- Welche (Noise -> third party code) kann weggelassen werden.

**Beispiel**
- Bis zu 50 % Code reduction für Microsoft für die .NET-Framework auf .NET 6.


## Performance Awareness
-  Jedes Team sollte Performance Aware sein
	- Bewusstes treffen von Trade-offs bezüglich Performance
- Stetiger Pfad -> Trade-Off Cycle

- Nach Implementation:
	- Wie wird Code at Scale ausgeführt -> Bauchgefühl
		- Wie könnte Memory-Last aussehen
		- Wie lange könnte der Job laufen
		- Wie schnell muss der Job laufen
	- Low-Hanging fruits
		- Was sollte "nicht" gemacht werden
		- Wo wird bewusst etwas anderes verwendet (LinQ vs nicht LinQ -> Readybility vs Performance)
	- Hot-Path verkleiner -> z.B. Allocations ausserhalb von Loops
	- Was soll priorisiert werden
	- Wann soll aufgehört werden

## Performance Loop
1. Profile using a harness
	1. Improve a hot paht
	2. Benchmark and compare
2. Profile improvements
3. Ship to production

### Profile using a harness
- Ist Problem isolierbar -> dann nutze Harness
	- Simple Applikation schreiben, welche nur das Problem ausführen kann

- Compile and execute in Release mode
- Runs a few seconds and keeps overhead minimal -> "Kein Kaltstart"
- Disable tiered JIT -> Code soll schon vor JIT optimiert werden
- Emit full symbols -> Dammit Call-Stack usw. im Profiler angeschaut werden kann

#### Memory Characteristics
- Memory-Allocations ist eines der grössten Probleme
- Iterative gains on the hot-path will lead to overall improvements

#### CPU Characteristics
- Braucht mehr effort -> Eventuell müssen Domain-Spezifische Algorithmen überarbetiet werden etc, einlesen etc.
### Improving
- Nichts optimieren wenn keine genügende Testabdeckung
- Particular Blog lesen

### Benchmark
#### Extract Code
- Copy and paste relevant code
- Adjust it to the bare essentials to create a controllabel Env
- Trim down to relevant behaviors
- DI-Container rauswerfen
- Remove IO-Operationen


#### Best Practices
- Single Responsibility -> Benchamrk misst nur etwas
- No side effects
- Prevent doead code eliminiation
- Delegates heavyy lifting to the framework
- Explizit
	- Kein implizites casting
	- Explicit types were necessary
- Avoid running any other ressource-heavy processes while benchmarking


## Prevent Regression
Bei .NET:
- ResultComparer Tool
- 