>[!Definition]
>Eine **Architekturbeschreibung** beschreibt die Umsetzung der **funktionalen** und **nicht-funktionalen** Anforderungen, welche an ein System gestellt werden..

Die Anforderungen können dabei aus:
- übergeordneten Anforderungsdokumenten (z.B. Lastenheft)
- übergeordneten Systemen (z.B. Schnittstellen)
abgeleitet werden.

Der Nutzen der Architekturbeschreibung liegt in:
- Entwurf und Dekomposition der [[Softwarearchitektur|Architektur]]
- Grobdesign der [[Komponente|Komponenten]]
- Kommunikation der Informationen an die Stakeholder.

Die Architekturbeschreibung wird initial ins "Sprint 0" erstellt und bildet die bisher bekannten Anforderungen ab.
Danach wird sie laufen in Sprints angepasst.

Meistens existieren Vorlagen, z.B.:
- [[arc42]]
- [[SA4D]]

## Inhalt
### Einführung mit Systemübersicht und Kontext
- Welches Problem löst das System?
- Wie löst das System das Problem
- Wer Benutzt das System
- Annahmen und Einschränkungen

#### Kontext
Die Kontextabgrenzung zeigt das zu entwickelnde System in seinem Kontext (geschäftlich und technisch)

-> Kann gut mit einem Kontextdiagramm veranschaulicht werden.

### Schnittstellen nach Aussen
Dokumentiert werden Externe Schnittstellen, welche **exportiert und importiert** werden. Zusätzlich auch **Benutzerschnittstellen**.

Meist im **separaten** Dokument beschrieben und es werden Kaptiel referenziert.

### Architektonische Sichten
Die unterschiedlichen Sichten auf ein System aus unterschiedlichen Perspektiven auf **hohem Abstraktionsniveau**.

- [[arc42]]
- 4 + 1-Sichten-Modell
- [[C4-Modell]]

#### Bausteinsicht
Die Bausteinsicht zeigt die Funktionalität des Systems auf unterschiedlichen Flughöhen. Ideal ist hierfür das C4-Modell.

Pro System werden mehrere Ebenen Dokumentiert:
- Teilsystem / Services z.B. Block-oder Kopmpnentendiagramme.
- Komponenten -> Komponentendiagramme.
- Code: i.d.R. Klassendiagramme und Sequenzdiagramme.

**Richtlinien**
- Keine Reverse-Engineering von Diagrammen aus Code
- Nur interessante / hilfreiche Stellen dokumentiert
- Auf das Notwendigste reduzieren.

#### Verteilungsschicht
Die Verteilungssicht zeigt auf welchen Hosts die Systeme eigensetzt sind:
- Sind mehrere physische Hosts eingesetzt?
- Auf welchen System wird welche Komponente eingesetzt?
- Was sind die Anforderungen an dieses System?
- Wie sind die Systeme konfiguriert?
- Wie wird die Software verteilt?
- Wie werden sie in Betrieb genommen.


### Querschnittsthemen
Zu den Querschnittstehmen gehören folgende Punkte:
- **Datenverarbeitung**
	- Struktur der persistenten Daten.
	- Beziehungen der persistenten Daten ([[Entity Relationship Model (ER-Modell)]])
	- Wie werden die Daten gespeichert?
	- Wie wird die Konsistenz sichergestellt.
- **[[VSK/Integrations und Systemtests/Teststrategie]]**
	- Wie wird das System und die Komponenten getestet.
- **Wichtige Schnittstellen**
	- Interne Schnittstellen zwischen Komponenten.

### Designentscheide
- Was sind die Überlegungen welche beim Design des Systems gemacht wurden?
- Welche Randfälle sind bewusst (nicht) abgedeckt?
- Welche Techniken werden bewusst (nicht) verwednet?
- Bestimmte Programmierparadigmen, Patterns
- Welche Libraries, Frameworks und Laufzeitumgebungen wurden verwendet.

### Qualitätsanforderungen
- Wie viele Daten pro Zeiteinheit muss das System verarbeiten können.
- Wie werden Daten gelöscht.
- Wie werden Daten gesichert.
- Wie schnell kann ein System wiederhergestellt werden.
- 