>[!Definition]
>Ein Kommunikationsprotokoll ist eine Vereinbarung, wie zwei Maschinen miteinander Kommunizieren. (Für verteilte Systeme ist dies meist auf der Anwendungsschicht.)

**Bestandteile**
1. **Definition des Übertragungskanals**:
	- Definition des Übertragungskanals ([[TCP]]/[[UDP]]).
	- Definition der Konfiguration des Kanals.
	- Definition der Anforderungen an den Kanal (z.B. Bandbreite, Latenz, usw.)
2. **Definition der Nachrichten Struktur**
	- Wie ist die Nachricht aufgebaut?
	- Existieren Stoppzeichen.
	- Welche Metadaten (ID, Version, usw.) gehören zu einer Nachricht?
3. **Definition aller möglichen Nachrichten**
	- Definition aller möglichen Nachrichten.
	- Definition aller Datentypen.
	- Definition aller Datenformate.

**Beispiel**
Ein Nachricht kann über Stopzeichen oder über die Länge definiert werden:
![[kommunikationsprotokoll.png]]


## Nachricht
Nachrichten sind der grösste Teil eines Kommunikationsprotokolls und folgen einem **generellen Nachrichtenformat**:

Eine Nachricht ist praktisch immer wie folgt gegliedert:

| Kategorie | Beschreibung                                                                                                                                              |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID        | - Identifiziert die Nachricht (z.B. GET, POST, usw.)<br>- Bei zustandsbasierten Protokollen teilweise nicht nötig (oder wenn es nur eine Nachricht gibt.) |
| Argumente | - Einfache Datentypen<br>- Strukturen oder Arrays<br>- Referenzen                                                                                         |
