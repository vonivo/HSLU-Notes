---
aliases:
  - SOA
---
Durch die SOA wird die Abstraktion und Granularität eine Ebene höher. Eine zu grosse Applikation kann in einzelne Services aufgebrochen, oder Teile davon in Services herausgebrochen werden.

**Beispiel**
- Kunden und Artikel sind zwei sehr lose (Sub-)Domänen, die von fast allen Prozessen benötigt werden.
- Diese bieden Teilen werden in eigene Services ausgelagert.


>[!Definition]
>Services sind **fachlich orientiert** und **technologieneutral**. Sie kapseln sauber abgegrenzte Subdomänen in eigenständige, verteilte Dienste, welche von einer übergeordneten Applikation zur Realisierung eines Businessprozess genutzt werden.
>

## Eigenschaften
- Ein Service verfügt über eine wohldefinierte Schnittstelle.
- Die Services sind in einem Verzeichnisdienst eingebunden und werden dynamisch gesucht und gebunden (**binding**)
- Die Kommunikation kann über (fast) beliebige Protokolle erfolgen ([[VSK/RPC/RPC|RPC]], [[CORBA]], [[HTTP]], SOAP, REST, etc.)
- Abhängigkeiten zwischen Services meist eine synchrone Kommunikation


## Vorteile
- SOA führt implizit zu einer fachlichen Entkopplung.

**Beispiel**
Zwei Applikationen (Domänen) benötigen teilweise dieselben Daten, und beide wollen der «Master» sein.
![[SOA1.png]]
=> **inakzeptable, zyklische** Abhängigkeit

Die gemeinsamen Teile als Subdomäne in einen neuen Service X auslösen:
![[SOA2.png]]

## Gefahren
- Spätestens mit SOA wird eine Architekturebene erreicht, die viele Interpretationen, Fehler und Missverständnisse erlaubt.
- SOA ist tatsächlich «nur» ein Konzept, und völlig losgelöst von einer konkreten Technologie oder gar Produkt