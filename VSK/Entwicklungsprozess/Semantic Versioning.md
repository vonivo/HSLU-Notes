Eine semantische Version beschreibt eine Software-Version mit 3 Zahlen:

- **Major**-Rlease (**X**.x.x): Wird inkrementiert, wenn es Breaking-Changes in der API, fachlichen Funktionen gibt, welche dazu frühen, dass es nicht mit früheren Versionen kompatibel ist.
- **Minor**-Release(x.**X**.x): Erweiterung einer API, der fachlichen Funktionen oder Konfiguration, welche aber vollständig rückwärtskompatibel sind.
	- Keine Änderung nötig, falls neue Funktionalität nicht benötigt wird.
- **Bugfix/Maintenance** (x.x.**X**): Reine Korrektur oder Änderung in der Implementation, vollständig rückwärtskompatibel und keinerlei v