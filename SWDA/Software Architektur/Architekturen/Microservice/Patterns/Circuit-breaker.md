Bei einer Kommunikation von zwei Services, z.B. der [[Gateway]] zu einem Service. Hier wird nun eine **circuit-breaker-Proxy** dazwischen gelegt.

- Dieser Proxy prüft permanent, wie lange die Requests im Schnitt laufen.
- Wird ein Threshhold überschritten, unterbricht der Proxy die Verbindung und bricht alle weiteren/neuen Request sofort ab. (**fail fast**)
- Nach einem konfigurierten Timeout öffnet der Proxy die Verbindung wieder und prüft erneut.

**Vorteile**:
Bei einer Störung/Ausfall werden weniger Ressourcen verschwendet, Aufrufer brechen schneller ab.