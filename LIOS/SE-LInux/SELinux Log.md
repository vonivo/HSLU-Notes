Alle verstosse genen eine Richtlinie von [[SE-Linux]] wird geloggt.
Die "raw message" ist in `/var/log/audit/audit.log` vorzufinden.

Die Logmessages können wie folgt ausgelesen werden:
- `ausearch` -> Ursprungsmeldung
- `sealert` -> Aufbereitet Meldung und Hilfe für Fixes

**Beispiel:**
```bash
[user@host ~]$ sealert -a /var/log/audit/audit.log
```
