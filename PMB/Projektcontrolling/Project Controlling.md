> [!info]
> Die Projektkontrolle umfasst alle Aktivitäten, um projektbezogene Abweichungen zwischen dem Plan- und dem IST-Zustand aufzudecke.

Die Ziele des Projectcontrollings sind:
1. Ist das [[Projekt]] in der Zeit.
2. Kann das Budget eingehalten werden?
3. Sind die nächsten Meilensteine erreicht.

Wenn diese Ziele nicht erreicht werden können, werden gegensteuernde Massnahmen ergriffen und Stakeholders informiert.

4. [[Risikoanalyse|Eintrittsindikatoren]] frühzeitig erkennen
	Bsp:
	- technische Risiken -> Task dauern länger
	- fehlerhafter Zeitplan -> wenn geschätzte Gesamtaufwände fortgesetzt und massiv steigen
5. Sind alle Ressourcen voll ausgelastet.
6. Post-Mortem-Analys
	- Signifikante Abweichung der Schätzung von dem IST-Aufwänden untersuchen und Ergebnisse nutzen, um die Schätzmethode im nächsten Projekt zu verbessern.
	- Verhältniszahlen für Phasenaufwände gewinnen.

## Klassisches Projectcontrolling
Mit einem [[Klassische Vorgehendsmodelle|klassischen Vorgehensmodell]] wird ein regelmässiger **Abgleich zwischen IST und SOLL** durchgeführt.

Dieser Vergleich geschieht auf der Ebene der [[Projektstrukturplan#Arbeitspaket|Arbeitspakete]] und wird in folgende Status unterteilt:
- offen
- erledigt
- in Arbeit

Das Kontrolling wird in Software-Projekten üblicherweise alle 14 Tage durchgeführt. In kritischen Phasen teilweise 2 mal Wöchentlich.

### Meilensteintrendanalye
Die [[Meilenstein]]-Trend-Analyse verdeutlicht den Stand und den Planungsverlauf eines Projekts anhand der [[Meilenstein|Meilensteine]].
Diese Analyse wird zu jedem Überprüfungszeitpunkt neu erstellt.
![[MeilensteinTrendAnalyse.png]]

### Fertigstellungsgrad
**Absoluter Fertigstellungsgrad**
- Der Fertigstellungsgrad wird nur für Arbeitspakete berechnet, welche bereits vollständig abgeschlossen sind.
- Damit der Fertigstellungsgrad genau ist, müssen die Arbeitspakete ausreichend klein sein.

**Relativer Fertigstellungsgrad**
- Miteinbezug des prozentualen Anteils der Aufgabenerfüllung der Arbeitspakete welche noch "in Arbeit" sind.
- Auchtung vor dem "fast-schon-fertig"-Syndrom

#### Restaufwand
Der Fertigstellungsgrad sollte grundsätzlich auf Basis der Werte:
- **geschätzter Aufwand**
- **verbrauchter Aufwand**
- **geschätzter Restaufwand**
berechnet werden.

### Verfahren
Bei grösseren Abweichunge zwischen SOLL und IST sollte genau hingeschaut werden:
- Ist der [[Ressourcenplan#Kritischer Pfad|kritische Pfad]] betroffen?
- Gibt es auswirkungen auf Endtermine?
- Probleme mit der Ressourcenvertielung?
- Risiko-Eintrittsindikator?

#### Restaufwandschätzung RAS
Die RAS ist die Schätzung, wie viel Aufwand absehbar noch benötigt wird um ein Arbeitspaket fertigzustellen.
$SOL - IST - RAS = \text{wahrscheinliches Gesamtergebnis für das Arbeitspaket}$
=> positiver Wert: Vorsprung
=> negativer Wert: Verzug

Das SOLL, IST und die RAS werden in einer Tabelle aufgelistet um eine Überblick über das Projekt zu erhalten:
![[RAS.png]]

### Regelkreis
- Zielsetzung
- Planung
- Datenerfassung
- SOLL-IST-Vergleich
- Abweichungsanalyse
- Massnahmen
- Erfogskontrolle

## Agiles Projectcontrolling
Während eines Sprint dient das Sprint-Taskboard zur Fortschrittskontrolle.
Ebenfalls wird am Daily-Scrum kurz angegeben wo gerade Schwierigkeiten bestehen und wie der Fortschritt der Arbeiten ist.

### Srpint Burndown Chart
Das Sprint Burndown Chart ist eine Grafik welche Zeit, wie der Sprintfortschritt im Vergleich zum Optimalfall gerade aussieht:
![[SprintBurnDown.png]]
### Sprint Review
Das Sprint Review dient zur Validierung der Sprintziele.
Beim Sprint-Review nimmt das gesammte Team, der ProductOwner sowie Stakeholder teil.

Das Team demonstriert die Software welche in diesem Sprint implementiert wurde und wenn nötig werden Anpassungen am [[Product Backlog]] und dem [[Releaseplan]] vorgenommen.

### Sprint Retro
Die Sprint Retrospektive dient dazu um zu überprüfen was in einem Sprint gut bzw. nicht so gut verlaufen ist.
Dabei wird versucht der Workflow des Teams sowie deren Prozesse zu verbessern.

### Project Burndown
Der [[Product Backlog]] kann sich im laufe eines Projekt stark ändern, daher wird am Ende jedes Sprints die Summe aller Aufwände der noch zu erledigenden [[Product Backlog Item|Product Backlog Items]] in den **Project Burndown Chart** eingetragen.

Dieser Chart zeigt wie der Sprint Burndown den verbleibenden Aufwand in Relation zur Verbleibenden Zeit.
![[Project_Burndown.png]]