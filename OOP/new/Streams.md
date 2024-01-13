Als Stream bezeichnet man einen kontinuierlichen Fluss an Datenelementen
- Ende der Menge ist am Anfang nicht bekannt
- Kann in kleinen Einheiten laufend verarbeitet werden
- Datenrate kann variieren (je nach Quelle)
- Kein wahlfreier Zugriff

Streams eigenen sich gut für den Umgang mit grossen Datenmengen

Ein Datenstrom muss nicht binär sein, es kann auch ein Strom aus anderen Datenobjekten sein (Personen, Temperaturen)

Die Stream API verarbeitet primär Objekt Ströme

Java Package `java.util.stream`

Stream API ist eng mit [[Lamdas]] verknüpft

## Best Practices
- Darauf achten das man auch deklarativ effizient programmiert
- Nur einsetzen wenn vollständig klar ist was passiert
- So früh wie möglich filtern um die Datenmenge zu reduzieren
- Bei [[Datentyp#Elementare Datentypen|Elementaren Datentype]] die speziellen Streams verwenden (IntStream, LongStream, etc.)
- **Die Stream API ist etwas ganz anderes als die [[IO Streams]]**
# Aufbau
Eine Pipeline (Verkettung von Funktionen) besteht aus den folgenden Elementen:
- **Supplier** → stream(…) oder Stream.of(…)
	- Quelle
- **Intermediate** → z.B. sort(…), filter(…), map(…)
	- Liefert wieder einen Stream
- **Temrinal** → foreach(…), max(…)
	- Liefert **ein** Ergebnis oder einen void
	- Der Stream kann nicht weiter gebraucht werden

Erzeugt wird ein Stream mit stream(…)
```java
final List<Temperatur> verlauf = new Arraylist();
verlauf.stream();
```

Danach könne beliebig viele Intermediate Funktionen auf den Datenstrom angewendet werden.

EIn Stream kann auch Deklarativ erzeugt werden:
```java
Stream.of("A","B","C");
```

Es gibt auch Stream für [[Datentyp#Elementare Datentypen|Elementare Datentype]] 
```java
IntStream.range(0,10);
```
Diese sollte unbedingt verwendet werden da sie einen viel effizientere Umgang mit elementaren Datentypen erlauben
## Beispiel
In diesem Beispiel wird in einem Verlauf aus Temperaturen Werte herausgefiltert, die Liste sortiert und [[Logging|geloggt]]. 

```java
verlauf.stream()
	.map(t -> t.getCelcius())                 // Von den Temperatur Objekten den Celcius Wert auslesen
	.filter(c -> (c >= 20.0f && c <= 25.0f))  // Alle Temperaturen zwischen 20 und 25 Grad auslesen
	.sorted()                                 // Die Temperaturen sortieren
	.forEach(v -> LOG.info("{} C", v))        // Jede Temperatur wird geloggt
```

### Nützliche Funktionen 
```java
// values printen
verlauf.stream().forEach(System.out::println)
// minimum
verlauf.stream().min();
// Alle Elemente in eine Collection übertragen
verlauf.stream().collect(Collectors.toSet());
```