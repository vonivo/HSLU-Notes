>[!Definition]
>Ein **Systemtest** prüft die gesamte Wirkungskette eines Softwareprodukts, also alle Aspekte, die mit [[Unit Tests]] und [[Integrationtests]] nicht abgedeckt werden.

Ein potenziell auslieferbares Produkt muss:
- Ausserhalb der Entwicklungsumgebung getestet werden.
- Eine Bedienschnittstelle zur Verfügung stellen.
- Mit anderen Applikationen und Systemen interagieren.

>[!Info]
>Die Testumgebung, in welcher die Systemtests laufen, sollte möglichst nahe an der produktiven Umgebung sein.


## Herleitung
Systemtest werden aus:
- Akzeptanzkriterien,
- Anforderungen,
- [[Use-Cases]]
hergeleitet.

**Nicht-funktionale Anforderungen** werden dabei in funktionale Anforderungen umgewandelt. Last-/ Performance- / Stress- / Security- und Robustnesstests sind ebenfalls Systemtests.

## Dokumentation
Systemtests werden als [[Regressionstests]] in weiteren Entwicklungsschritten wiederverwendet. Daher müssen Systemtests **nachvollziehbar dokumentiert** sein, um **reproduzierbare** Tests zu gewährleisten.

Wichtige Bestandteile eines Testdrehbuchs:
- **Vorbedingungen**
- **Test-Schritte mit Eingaben**
- **Erwartete Resultate.**


