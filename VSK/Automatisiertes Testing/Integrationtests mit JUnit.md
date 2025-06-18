>[!Info]
>JUnit kann zur Automatisierung von fast allen Testarten benutzt werden.

- Integrationtests werden nach dem Namensschema `XyzIT.java` benannt und befinden sich unter `src/test/java`.
- Der Unterschied zu [[Unit Tests]] ergibt sich **nur** durch den Zeitpunkt der Ausführung und deren Laufzeit-Abhängigkeiten. (z.B. Verify [[Maven]]-Phase)


Die Aufteilung zwischen Unit- und Integrationstests wird oft häufig kontrovers diskutiert.
- Explizit Gedanken zu Aufteilung machen und sich im Team darauf einigen.
- Je mehr Unit-Tests desto besser.
