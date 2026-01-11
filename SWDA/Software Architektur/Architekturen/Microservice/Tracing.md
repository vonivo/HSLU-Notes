Wenn ein Service eine Anzahl von Folgeaktivitäten (weitere Services)
aufruft, und diese asynchron und durch Queues verzögert ausgeführt werden, ist eine (Fehler-) Verfolgung des gesamten Request (sehr) schwierig
- Analyse der Log-Dateien zwar möglich, aber aufgrund des fehlenden zeitlichen (synchronen) Kontextes praktisch nicht möglich  gemeinsame Zeitbasis aber trotzdem wichtig!

**Lösungsansatz**: Man verpasst jedem Client-Request einen Fingerabdruck, die **Correlation-ID** und reicht diese konsequent an alle Unter- bzw. Folgeaufrufe weiter.
- Somit wird unabhängig vom zeitlichen und örtlichen Kontext ein kompletter Request relativ einfach nachvollziehbar.


## UUID
Universally Unique Identifer bestehen aus einer 16-Byte-Zahl, welche in hexadezimal notiert und in fünf Gruppen unterteilt wird.
`4e6abea6-d18a-49c1-a7b0-4f57702e6602`

Es existieren 5 Typen von UUIDs


## Empfehlungen
- Correlation-IDs nicht auf Ebene der fachlichen Schnittstelle einfügen.
- Correlation-ID möglichst in den Kontext / Metadaten verschieben.
- Correlation-IDs nur dann als UUId einsetzen, wenn kein fachliches eindeutiges Attribute verwendbar ist.

## Tracing-Server
- Zipkin
- Jaeger

