Eine User Story ist ein kurzer Text, der eine Interaktion von einem Benutzer mit dem System beschreibt.

Diese Beschreibung dient als Ausgangspunkt für die Kommunikation und Umsetzung einer [[Requirement|Funktionalität]].

Eine User Story wird als gut befunden, wenn sie die Kriterien nach [[INVEST]] erfüllen.

## Struktur
**Title**
- Kurze prägnante Bennenung

**Beschreibung**
- Wer möchte was?
- Durch welche Funktionalität will er den Nutzen realisieren?
- Warum will er das tun?

=> Schema: "Als \[Rolle/Akteur] möchte ich \[Funktionsbeschreibung] damit \[Begründung]".

**Akzeptanzkriterien:*
- Wie kann festgestellt werden, ob die User Story entsprechend den [[Requirement|Anforderungen]] umgesetzt wurde?
- Beantwortet die Frage, was getestet werden soll.

**Ergänzende Beschreibung**
- typisch als Link auf einen Use Case, GUI-Protoyp etc.

## Beispiel
**Title**
- CSV-Export

**Beschreibung**
Als Benutzer möchte ich die Daten meiner Konten per CSV-File herunterladen können, um damit ausserhalb von "TwentyFeet" weitere Auswertungen und Berichte zu erstellen.

**Akzeptanzkriterien:*
- Ich kann die Daten für jedes meiner Konten herunterladen.
- Es sind alle Werte in der CSV-Datei enthalten, die ich auch beim jeweiligen Konto bei "TwentyFeet" einsehen kann.
- Ich kann die Daten für alle bei "TwentyFeet" zur Auswahl stehenden Berichtszeiträume ausgeben lassen.

**Ergänzende Beschreibung**
- folgen später