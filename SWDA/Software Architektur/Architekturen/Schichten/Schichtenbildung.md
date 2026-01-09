>[!Definition]
>Schichtenbildung beschreibt die Gliederung einer Applikation in aufeinander aufbauenden, funktional getrennten Schichten, welche
>- über wohl definierte Schnittstellen kommunizieren
>- Nur von tief liegenden Schichten Abhängig sind
> - Keine Schichten überspringen (ausser offene Schichtenarchitektur)

Schichten können zur Strukturierung innerhalb eines Systems sowie systemübergreifend genutzt werden.

Werden Schichten physisch verteilt spricht man von [[Tier]].

![[Layering.png]]

## Schichten
Die Schichtenbildung kann nach folgenden Attributen geschehen:
- Logik / Funktionalität
- Technologie
- Abstraktionsebene

>[!error]
>Java Packages sind nicht geeignet für die Schichtenbildung. Packages sind zur logischen Gruppierung und Kapselung von Code. Besser wäre z.B. Module von [[Build-Werkzeug|Buildwerkzeugen]]

## Potential
- Die Schichtenbildung ist eine **fundamentale Grundlage**, um [[Verteilte Applikation|verteilte Applikationen]] zu realisieren.
- Eine Schichtengrenze eignet sich gut, um auch eine Tiergrenze zu realisieren.

So wird aus folgenden [[Monolithische Architektur|deployment Monolith]]
![[Schichtenbildung_1.png]]
Schnell und ohne Modul $A$ oder Modul $B$ zu ändern eine verteilte Applikation:
![[Schichtenbildung_2.png]]


## 3 Schichtarchitektur
Sehr häufig wird in drei Schichten aufgeteilt:
- [[Präsentations-Schicht]]
- [[Businesslogik]]
- [[Persistenzschicht]]

Diese Aufteilung **lohnt sich praktisch immer**, unabhängig von der physischen
Verteilung! ([[Single Responsibility Principle (SPR)]], SoC, -> [[SWDA/Software Architektur/Modularisierung|Modularisierung]])


## Pro und Contra
**Pro**
- Bessere Strukturierung, einzelne Schichten kleiner und einfacher, somit besseres und schnelleres Verständnis.
- Grössere Chance auf Wiederverwendung (einzelner Layers).
- Höhere Flexibilität, z.B. Austausch einzelner Schichten.
- Bessere Skalierbarkeit (primär vertikal)
- Einfachere und präzisere Planung/Schätzbarkeit
- Parallele und getrennte Entwicklung möglich
- Zentralisierung der Businesslogik

**Contra**
- Komplexität des ganzen Systems wird grösser
- Mehr Schnittstellen, mehr Aufwand, mehr Planung
- Schichten sind technisch – wo bleibt die Fachlichkeit


**Bilanz**
- Datentypen an wichtigen Schichtengrenzen bewusst «brechen». Vorteile überwiegen klar, auch wenn es viele Nachteile hat (siehe unten)
- Schichten funktionieren hervorragend (SLA), und ergeben sich fast von selbst
	- Herausforderung: Ab wann ist ein Interface sinnvoll / nötig
	- Zu viele Schichten gibt es (fast) nicht

=> Nicht die Anzahl (oder «Höhe») der Schichten ist die Herausforderung, sondern zu erkennen, wann eine Schicht (bzw. ein ganzer Stapel) zu breit wird!