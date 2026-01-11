>[!Definition]
>Laufzeitmetriken sind explizite in die Software eingebaute (programmierte) **Messpunkte**, welche Rückschlüsse auf die _Leistung_ eines Systems erlauben.

Es gibt verschiedene Arten von Messpunkten:
- Einfacher Zähler: Anzahl Ereignisse kumulieren.
- Messwert (gauge): Absoluter Wert (z.B. Elemente in einer Queue)
- Meter (meter): Messwert pro Zeiteinheit (Ereignisse pro Minute)
- Histogramme: Statistisches Verteilung von Messwerten

Die grosse Herausforderung ist die Auswahl eines geeigneten Messpunkts für eine bestimmte Grösse in dem System:
- Betrifft die Art des Messpunkts
- Betrifft den Ort des Messpunkts


## Beispiel Drop Wizard
Sehr einfache API für Metriken:
- Zentrale Registry, Identifikation über Strings.
- Verschiedene Metriken (Counter, Gauge, Meter etc.).
- Vorbereitete Metriken (Instrumentierung) für einige bekannte Frameworks.
- Diverse Adapter zur Extrahierung / Freigabe der Messdaten.

```java
// Zentrale Metrik-Registry aktivieren…
final MetricRegistry metrics = new MetricRegistry();
// …und eine konkrete Metrik (meter) registrieren.
metricPrimeProbe =
	metrics.meter("ch.hslu.swe.primefinder.prime-probe");
…
// Ein Ereignis (Metrik) markieren (typisch n-fach).
metricPrimeProbe.mark();
…
// Manuelle Auswertung / Abfrage der Metrik (z.B. über Logging!)
LOG.info("Generate[Total:{}, Rate:{}/s]",
metricPrimeProbe.getCount(),
metricPrimeProbe.getMeanRate());
```

## Vsiualisierung
- Regelmässiges [[SWDA/Software Architektur/Architekturen/Microservice/Logging|Logging]] kann eine Technik sein
- Weiterleitung an Zugriffspunkte von spezilisierten Monitoring-Systme
	- Prometheus
	- InfluxData
	- InfluxData
- Zugriff eines Visualisierungssystems:
	- Grafana
	- Graphite
	- Kibana
