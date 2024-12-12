Grundprinzip: Least Privilege Identifizierung → Authentifizierung → Autorisierung → Verantwortlichkeit

Identifizierung → Welcher Benutzer Authentifizierung → Ist es der richtige Benutzer Autorisierung → Rechteprüfung Verantwortlichkeit → Nachvollziehbarkeit

## Loginprotokolle

Aufbau:

1. Setup
2. Login

Challenge Response Verfahren (sym):

1. Setup (Schlüssel teilen)
2. Bob challenged Alice
3. Alice berechnet Response
4. Bob beurteilt ok/not ok

Challenge Response Verfahren (asym):

1. Setup
2. Bob challenged Alice
3. Alice signiert
4. Bob verifiziert Signatur

→ Kann auch mit Zertifikat erfolgen

### Angriffe

- Direkter Angriff
- Abhörender Angriff
- Aktiver Angriff