Eine Architektur ist eine Abstraktion, welche etwas zusammenfasst und vereinfacht darstellt.

Die Softwarearchitektur beschreibt ein System durch:
- Sub- und Teilsysteme
- Schichtung
- Zwielben-Schichten
- Verteilung.


Softwareteile innerhalb dieser Architektur sind Komponenten welche nach Aufgaben/Zuständigkeiten oder nach Technologie gegliedert werden.

Die Beziehung dieser Komponenten kann sich auf folgendes belaufen:
- Abhängigkeiten
- Schnittstellen
- Daten- und Kontrollflüsse (Kommunikation)
- Transaktionen
- Deployment
- etc.

>[!Definition]
>Softwarearchitektur definiert sich durch die Kernelemente eines Systems, welche als Basis für alle weiteren Teile, nur schwer und aufwändig verändert werden können.

>[!Info]
>**Definition nach Fowler:**
>Die Architektur repräsentiert die signifikanten Designentscheidungen die ein System festhalten, wobei die Signifikanz an den Kosten von Änderungen bemessen wird.



## Aspekte
- Grundlegende Struktur:
	- Schichten, Client/Server, n-Tiers Services etc.
	- Art der Applikation und des Deployments (**äussere Struktur**)
	- [[Architekturmuster]] und -prinzipien(**innere Struktur**)
- Kommunikation und Verteilung
	- Verteilbarkeit, Parallelität, Performance, Robustheit, Resilienz
	- Kommunikationsmuster (**Synchron/Asynchron**)
	- Interaktion der Systeme, Transaktionalität
- Eingesetzte Technologie
	- Userinterface ([[Fat-Client|Fat-]],[[Thin-Client|Thin-]], [[Rich-Client|Rich-]]Client)
	- Persistenz der Daten (Frameworks, OR-Mapping, NoSQL)
	- Referenzarchitekturen

## Verschiedene Arten von Applikationen
- Einzelbenutzerapplikationen
	- Eher klein, eventuell sogar "nur" eine Mobile-App
	- Lokale Persistenz, eher wenig komplexe Funktionalität
- Mehrbenutzerapplikation
	- Unternehmensapplikation
	- Zentrale Services und Daten beliebig hohe Komplexität
	- Typisch in mehreren (Teil-)Systeme aufgebrochen.
- Internetanwendung
	- Typisch mit Web-GUI, beliebig viele Benutzer
	- Verteilte Datenspeicherung, Skaliert, beliebige Komplexität

## Architekturstile im Verlaufe der Zeit
1. Es führte oft zum berühmt-berüchtigten «[[Fat-Client]]» und einer überforderten Datenbank
	- Vorteil: Zentrale Datenhaltung, hohe Konsistenz (RI,Trigger,SP)
	- Preis: Transaktionen, Locking, Ressourcen, Verteilung,…
- «Im Kleinen» z.B. für lokale (Einbenutzer-)Apps auf Handys funktioniert das gerade sehr gut!

## Design vs. Architektur
Fast alle [[Designprinzipien]] können auch bei Architekturfragen benutzt werden:
- Modularisierung durch Komponenten, Schnittstellen, Packages.
- Gruppierung dieser «Teile» zu (Sub-)Systemen.
- Nutzung von verschiedenen Mustern zur Strukturierung.

>[!error]
>Die grosse Herausforderung: Alle diese Prinzipien auf den **unterschiedlichen** **Abstraktionsebenen** angemessen zu befolgen und zu beurteilen.

