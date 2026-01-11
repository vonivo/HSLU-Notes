In klassisches Applikationen haben wir wenige Dienste die meistens in Deployment statisch konfiguriert sind:
- IP-Adressen und Ports mit fix zugewiesenen DNS
- Konfiguration mit verschiednen Umgebungen

In [[Microservice Architektur]] haben wir viel mehr Services und dadruch eine viel höhere Dynamik.
Damit dieser Aufwand nicht manuell gemacht werden muss (Aufwändig, Fehleranfällig, Inflexibel) existieren spezielle Service Discovery Dienste.

## Beispeil Consul
Sehr vereinfacht erklärt sind Service-Discoveries vergleichbar mit «lokalen» DNS. Sie ordnen logischen Namen einen (oder mehrere) Services zu (IP und Port etc.)
- Alternativer Vergleich: RMI-Registry bei RMI

Auch hier wachsen die Fähigkeiten weiter, und Service Discoveries können auch eine Art Load-Balancing übernehmen, indem Sie die registrierten Services selbständig monitoren und Anfragen zählen