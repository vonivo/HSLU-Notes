>[!info]
>Ein Requirement ist jede Anforderung eines Stakeholders und jede Eigenschaft, die ein geplantes System erfüllen muss.

Eine Requirement-Spezifikation ist jede Repräsentation eines oder meherern Requirements.


## Strukturierung
Die Strukturierung von Requirements werde grundsätzlich in diese drei Ebenen unterteilt:
- High-Level-Ebene -> um den Überblick über das [[Projekt]] zu erlangen bzw. behalten.
- Strukturierungsebene -> Zusammenhänge der verschiedenen Artefakte werde ersichtlich
- Detailebene -> Spezifiziert Feingranular den Inhalt. Muss vor der Umsetzung bereit sein.
![[Requirement_levels.png]]
## Arten von Anforderungen
Anforderung können in zwei verschiedene Arten unterteilt werden.

### Funktional
Funktionale Anforderungen bestimmen:
- Was ein System leistet.
- Welche Dienste das System anbietet.
- Welche Eingabe wie verarbeitet, abgespeichert und ausgegeben werden.
- Wie sich ein System verhaltet.

### Nichtfunktional
Nichtfunktionale Anforderung sind meist die Anforderungen, welche schwierig zu erreichen sind und strecken sich über jede funktionale Anforderung mit.
Dazu gehören:
- Wie das System die Funktionen abarbeitet.
- Wie die Qualitätsanforderungen sind. (Performance, Zuverlässigkeit, ...)
- Anforderungen an die Benutzbarkeit des Systems.

Nichtfunktionale Anforderung sind Qualitäten, welche das System attraktiv, benutzbar, schnell oder verlässlich machen.

Da sie Qualitätsaspekte beschreiben, besitzen sie Wiederverwendungspotential über das [[Projekt]] hinaus.

Nichtfunktionale Anforderungen müssen unbedingt messbar formuliert werden.
![[NichtfunktionaleAnforderungen.png]]

## Struktur
Ein Anforderungskatalog (Klassisch) oder ein [[Product Backlog]] (agil) sollte folgende Informationen enthalten:
- Titel -> Kurzer aussagekräftiger Name / Title der Anforderung
- Beschreibung -> Eine stichwortartige aber präzise Beschreibung der Anforderung.
- Priorität
	- 1 = Hight (Höchste Priorität)
	- 2 = Medium (Könnte in nächsten Release verschoben werden)
	- 3 = Low Priorität ist tief (eventuell ganz wegglassen)
- Status
	Der Status einer Anforderung wird üblicherweise in:
	- proposed -> Engegengenommen aber noch nicht akzeptiert.
	- Accepted -> Geprüft und akzeptiert.
	- postponed -> Geprüft und verschoben.
	unterteilt.

	Bei einem [[Agiles Vorgehensmodell|agilen Vorgehensmodell]] ist jede Anforderung im Status "proposed" bis sich bei einem Sprint-Planing dazu entschieden wird die Anforderung umzusetzen.
- Quelle -> Person oder Organisation welche die Anfroderung gestellt hat.
- Komplexität -> Die Einschätzugn des Aufwandes für die Umsetzung
	- Klassisch durch den Projektleiter
	- Agil durch Plaing-Poker
- Nutzen -> Stichwortartige beschreibung des Nutzens.
