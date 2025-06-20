[[Cybersicherheit|Cybersecurity]]:
Schutz von kritischer Systeme und sensibler Informationen vor digitalen Angriffen.

**Betriebssicherheit**
Fehlfunktionen treten nicht auf oder verursachen keine kritischen Schäden an Mensch und Maschine.


## Sichere Kommunikation
![[SicherheitInVerteiltenSystemen.png]]
1. `A` muss sicherstellen, dass `B` das korrekte System ist.
2. `B` muss sicherstellen, dass  `A` ein berechtigtes System ist.
3. Kein Drittsystem `C` darf die Kommunikation manipulieren können.
4. Kein Drittsystem `C` darf die Kommunikation mithören.

## Massnahmen
- **Zugriffsschutz**: Nur berechtigte Benutzer und Systeme können auf unser System regulär zugreifen.
	- Authentifizierung und Autorisierung.
- **Manipulationssicherheit**: Gesendete Daten können nicht verändert werden.
	- [[Digitale Signatur]]
- **Abhörsicherheit**: Keine geschützten Informationen gelangen nach aussen.
	- [[DMATH/Zahlentheorie/Kryptographie/Symmetrische Verschlüsselung|Symmetrische Verschlüsselung]] und [[DMATH/Zahlentheorie/Kryptographie/Asymmetrische Verschlüsselung|Asymmetrische Verschlüsselung]]
- **Nachvollziehbarkeit**: Wissen darüber, wie und von wem das System verwendet wurde.
	- Logs / Audit-Trails
