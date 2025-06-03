Bei Cut-Through wird das [[Frame]] unmittelbar nach dem Determinieren der Ziel-Adersse weitergeleitet.

**Charakterisitka**:
- Angemessen für Low-Latency-Anforderungen ($< 10 \mu s$)
- Kein FCS-Check
- Kann zu Bandbreiten-Fehlern führen, wen Switch zu viele Fehler propagiert.
- Keine Unterstützung für verschieden Übertragungsgeschwindigkeiten zwischen [[Frame Forwarding|Ingress- und Egress-Interface]].

## Fragment-Free
Die Fragment (Frag)-Free Methode ist ein Kompromiss zwischen Cut-Through und Fehlervermeidung.

- Frag-Free stellt sicher, dass das Frame mindestens 64 Byte lang ist um Runts zu vermeiden.
