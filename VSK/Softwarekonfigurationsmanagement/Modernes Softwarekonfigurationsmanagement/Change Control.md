Das Ziel von Change Control ist "Kontrollierte und nachvollziehbare Änderungen" an allen Softwarekonfigurationselementen durchzuführen. Das beinhaltete folgende Fragen:

- Darf und soll eine Änderung gemacht werden?
- Wer darf Codeänderungen machen
- Wo sollen Codeänderungen stattfinden (in welchem Release)
- Wer darf auf welchem Environment deployen?

In GitLab können viele solcher Regeln definiert werden.

## Change Control Board (CCB)
Das CCB koordiniert Änderungen pro Release und Umgebung.
Das CCB kann verschieden zusammengestellt werden:

- Kleiner Kreis von Seniors
- Releasemanager pro Release mit Stellvertreterregelung
- Senior pro Komponente mit Stellvertreterregelung
- N Peers

Das CCB legt fest, welche Änderungen, in Anbetracht des Risikos, in welchem Release gemacht werden: **Gatekeeping**.

Das CCB legt auch die Standardkorrekturregeln fest, z.B.:
- Unkritische Korrekturen von Releases mit gemeldeten Fehlern nach oben beheben 
(keine Regression nach oben, keine unnötigen Korrekturen nach unten)
- Kritische Korrekturen: Branches im Vorfeld nach unten zu allen noch von Kunden verwendeten Releases sowie Kommunikation mittels Critical-Known-Issue-Prozess (CKI) aufsetzen.

**Beispiel**:
![[ChangeControl.png]]
1. Unkritischer Fehler gemeldet in `2.2.2`
	  -> Korrektur in `2.2.2`, `2.2.y`, `2.x.y`, `3.1.y`, `3.x.y`, `MAIN`
2. Kritischer Fehler gemeldet in Release `3.1.1`, eingeführt auf dem MAIN zwischen `2.0.0` und `3.0.0` 
	  -> Korrektur in `MAIN`, `3.1.y`
	  -> Benachrichtigung aller Kunden welche `3.1.1` einsetzen