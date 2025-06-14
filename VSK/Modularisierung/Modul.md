>[!Definition]
>Ein Modul ist ein **in sich geschlossenen** Teil eines Programm-Codes. Dieser besteht aus einer Folge von bearbeitungsschritten und Datenstrukturen.

## [[VSK/Modularisierung/Kopplung|Kopplung]] und [[VSK/Modularisierung/Kohäsion|Kohäsion]]
Ziel ist es, die [[VSK/Modularisierung/Kohäsion|Kohäsion]] zu maximieren und die [[VSK/Modularisierung/Kopplung|Kopplung]] zu minimieren.
![[Komplexität_Module.png]]

## Kriterien des Modularen Entwurfs
**Zerlegbarkeit (Top-Down)**
Module sind Teilprobleme und sind unabhängig voneinander entwerfbar.

- Ein komplexes Softwareproblem in wird weniger komplexe Teilprobleme zerlegt. Diese Teilpro werden so verknüpft, dass sie möglichst unabhängig voneinander bearbeitet werden können.
- Rekursive Zerlegung, biss die Problem eine lösbare Komplexität haben.

**Kombinierbarkeit (Bottom-Up)**
Module sind unabhängig voneinander (wieder)verwendbar.

- Es sollen möglichst frei kombinierbare Software-Elemente angestrebt werden, welche in einem anderen Umfeld wiederverwendet werden können.
- Kombinierbarkeit und Zerlegbarkeit sind unabhängige Eigenschaften.

**Verständlichkeit**
Module sind unabhängig voneinander zu verstehen.

- Der Code eines Moduls soll ohne Kenntnis der anderen Module verständlich sein.
- Software muss unabhängig voneinander verstanden und gewartet werden können.

**Stetigkeit**
Kleine Anpassungen der Spezifikation führen zu kleinen Änderungen des Codes.

- Kleine Änderungen sollen auch nur ein kleiner Teil der Module betreffen, ab besten nur eines.

## Prinzipien der Modularisierung
**[[VSK/Modularisierung/Kopplung|Kopplung]] minimieren**
Schmale Schnittstellen,  um nur das wirklich Benötigte auszutauschen.

**[[VSK/Modularisierung/Kohäsion|Kohäsion]] maximieren**
Hoher Zusammenhalt innerhalb der Module.

**Information Hiding**
Das Modul ist gegen Aussen nur über eine Schnittstelle bekannt.

**Wenige Schnittstellen**
Minimale Anzahl der Schnittstellen (Aufrufe, Daten).

**Explizite Schnittstellen**
Aufrufe und gemeinsam genutzte Daten sind im Code ersichtlich.

**Wenige Abhängigkeiten**
Reduktion der Auswirkung von Änderungen auf andere Module.

## Vorgehen
1. Zerlegung (Top-Down oder Bottom-Up):
	- Wenig [[VSK/Modularisierung/Kopplung|Kopplung]] und viel [[VSK/Modularisierung/Kohäsion|Kohäsion]].
	- Information Hiding.
	- Wenige explizite Schnittstellen.
2. Beurteilung hinsichtlich der Kriterien:
	- Zerlegbarkeit: Module aufgeteilt und unabhängig bearbeitbar?
	- Kombinierbarkeit: Können Module wiederverwendet werden?
	- Verständlichkeit: Viel Kohärenz und wenig [[VSK/Modularisierung/Kopplung|Kopplung]]?
	- Stetigkeit: Auswirkungen von Änderungen
3. Falls Kriterien nicht zutreffen zu 1.
