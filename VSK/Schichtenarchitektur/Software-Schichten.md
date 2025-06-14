>[!Definition]
>Eine Softwareschicht ist eine organisatorische Einheit zusammengehöriger Module welche Schichtenweise aufeinander Aufbauen verwendet werden.
>
>Schichten sind oft eine technische Modularisierung entlang **organisatorischen** Einheiten. [[Komponente|Komponenten]] werden einer einzelnen Schicht zugeordnet.

![[Layer.png]]

>[!Info]
>Die Softwareschichten beschreiben die Modulhierarchie.
>Darüberliegende Schichten dürfen Methoden von darunterliegende Modueln aufrufen, jedoch nicht umgekehrt.


Eine Schichtenarchitektur ist die Basis für komplexe Architekturen.

## Deployment-Monolith
Typischerweise werden immer alle Schichten gleichzeitig angepasst und vollständig ausgeliefert.

## Schichten
**Presentation Layer (Anwendung)**
Darstellung und Benutzerinteraktion mit der Geschäftslogik.

**API-Layer**
Bereitstellung des Zugriffs auf die Geschäftslogik über eine [[Schnittstelle]].

**Business Layer**
Beinhaltet die Geschäftslogik

**Persistence Layer**
Abstrahiert den Datenzugriff.

**Database Layer**
Zugriff auf den Storage. (z.B. Definition des Schemas.)

## Beziehungen
![[Layer_interaction.png]]
- **A**: Okay
- **B** Zulässig, falls explizit vorgesehen ([[offene Schichtenarchitektur]]).
- **C**: Nicht zulässig

![[Layer_interaction2.png]]
Eine Klasse `P1` kann eine Methode `P2` aufrufen, indem eine Referenz übertragen wird. (**ohne Use Beziehung**).

**Beispiele**
- Callback
- Error-Handler
- usw.
