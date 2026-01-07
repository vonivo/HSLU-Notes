Siege [[Modul|VSK: Modul]], [[VSK/Deployment/Modularisierung|VSK: Modularisierung]], [[OOP/Modularisierung|OOP: Modularisierung]] 

- Die kleinste Einheit in der objektorientierten SW-Entwicklung stellt im Prinzip die Klasse dar.
	- Methoden (Verhalten) und Daten (Attribute, Zustand).
- Eine grosse Einheit stellt eine vollständige Applikation oder auch ein komplettes Softwaresystem dar.

>[!Definition]
>Die Modularisierung identifiziert zusammengehörige funktionale Teile welche zwischen diesen beiden Extrem liegt und bildet daraus Module.

- Module kommunizieren über **klar definierte Schnittstellen**
- Können **parallel** entwickelt werden.
- Sind einfacher verständlich
- können wiederverwendet werden.

=> Fundamentales Prinzip in der [[Software Architektur]]


## Kriterien zur Modularisierung
- [[VSK/Modularisierung/Kopplung|Kopplung]]
- [[VSK/Modularisierung/Kohäsion|Kohäsion]]
Die Kopplung und Kohäsion beurteilen wird auf allen Abstraktionsebenen immer wieder neu, die Anforderungen werden aber zunehmen strenger!

## Einfluss auf die Architektur
Die Modularisierung führt meistens zu einer vielfältig ausgeprägten, übergeordneten Struktur und Organisation aller Module in einem System.
- **Gruppierung:** Eine Menge von Modulen mit gemeinsamen Eigenschaften wird als Gruppe gehandhabt. (Mehrere Module welche z.B. Daten in je einem anderen Format exportieren)
- **Hierarchie**: Ein Modul fasst mehrere (Sub-)Module zu einem einzigen zusammen. (Beispiel: Persistenzmodul als Datenspeicher mehrerer Entitäten.)
- **Geschichtet:** Module können miteinander verkettet werden und so als Schichten betrachtet werden (z.B. [[OSI Referenzmodell]])

## Eigenschaften
- Kommunikation über **explizite Schnittstellen**
	- Die Schnittstellen sollen dabei möglichst einfach und schmal sein.
- Starke [[VSK/Modularisierung/Kohäsion|Kohäsion]]
	- Ein Modul sollte durch [[Single Responsibility Principle (SPR)]] und Separation of Concerns möglichst in sich geschlossen sein.

Durch diese Eigenschaften ergibt sich **Information Hiding** (Implementation des Moduls bleibt verborgen) und eine lose [[Kopplung]] (Die nur über die Schnittstelle mögliche Nutzung des Moduls fördert die möglichst lose Kopplung zwischen den Modulen.)


## Kriterien
1. **Verständlichkeit**
	- Die Module sind einzeln (und ohne Kontext) leicht verständlich.
2. **Stetigkeit**
	- Die Module haben eine hohe Beständigkeit, müssen also nicht bei jeder Wiederverwendung wieder angepasst werden.
3. **Zerlegbarkeit**
	- Die einzelnen Module sind maximal unabhängig voneinander und auf ein sinnvolles Minimum reduziert (SRP).
4. **Kombinierbarkeit**
	- Die entstanden, vorhandenen Module sind sinnvoll neu kombinierbar.


## Prinzipien
Prinzipien und Regeln für die Modulkohäsion:
- [[Release Reuse Equivalence Principle]] -> Usability
- [[Common Closure Principle]] -> Maintainablity
- [[Common Reuse Priciple]] -> Weniger Abhängigkeiten

Die drei Pinzipien arbeiten gegeneinander -> **Tradeoff**.


Prinzipien und Regeln für die Modulkopplung:
- [[Stable Dependencies Principle]]
- [[Stable Abstraction Principle]]
- [[Acyclic Dependencies Principle]]
