>[!Definition]
>Der Bug-Flow definiert einen Ablauf, wie mit gefunden Abweichungen von Soll-Zustand umgegangen wird. Durch ihn wird auch verhindert das Changes oder neue Anforderungen als Bug aufgenommen werden.

![[BugFlow.png]]

Durch Auswertungen erfasster Bugs können sehr viele Schlüsse gezogen werden, indem man diese Klassifiziert.

### ABC-Analyse
Mit dieser Analyse sollen die gefundenen Fehler sehr schnell, "aus dem Bauch heraus", kategorisiert werden. Dies kann nach Ursache, Fehlerbild, Technologie etc. sein.
Es sollte dabei nicht zu viele Kategorien geben.
Nun kann die Kategorie mit der grössten Fehlerzahl tiefer untersucht werden.

## Fehlerklasse

| Klasse   | Beschreibung                                                                                                    |
| -------- | --------------------------------------------------------------------------------------------------------------- |
| 1 low    | leichter Fehler, betrifft einzelnen Testschritt. Funktion bleibt im Wesentlichen gewährleistet.                 |
| 2 Medium | Betriebsstörender Fehler, Systemfunktion nicht beinträchtigt. Wesentliches funktioner, wenn auch eingeschränkt. |
| 3 High   | Schwerer Fehler, Auswirkungen auf Funktion, keine Auswirkung auf andere Funktionen/Systeme                      |
| 4 Urgent | Fataler Fehler, Auswirkung auf ganzes System -> Testabbruch                                                     |

## Reproduzierbarkeit / Beobachtungsgüte

| Klasse | Beschreibung                                                     |
| ------ | ---------------------------------------------------------------- |
| A      | Eindeutig festgestellter, belegbarer und reproduzierbarer Fehler |
| B      | Nicht ohne weiteres reproduzierbar, aber wiederholt aufgetreten  |
| C      | Nicht reproduzierbar                                             |

## Bug
>[!Definition]
>Ein Bug (Fehler) bezeichnet ein fehlerhaftes, entgegen der aktuellen Beschreibung (UC) festgestelltes Verhalten. Herkunft: produktiver Betrieb oder aus Testphasen resp. durch Testteam

## Change
>[!Definition]
>Ein Change (-Request; CR) bezeichnet eine gewünschte und definierte Änderung oder Erweiterung (oft auch Präzisierung) zu einer bereits bestehenden (und dokumentierten) Spezifikation ([[Use-Cases]]/Anforderung).

## Neue Anforderung
>[!Definition]
>Eine neue Anforderung liegt nur dann vor, wenn die gewünschte Änderung nicht auf einer bestehenden Beschreibung (UC) aufbaut oder diese um wesentliche zusätzliche Funktionalitäten ergänzt.

