>[!Definition]
>Eine Facade stellte eine einheitliche, zusammengefasste [[Schnittstelle]] zu einer Menge von Schnittstellen mehrerer Subsysteme zur Verfügung.
>- [[Structural-Patterns]]
>- [[Entwurfsmuster|Objektbasiert]]

![[Facade.png]]
- Eine Facade weiss, welche Subklassen für eine Anfrage zuständig sind, und delegiert dies weiter.
- Die Subklassen implementieren die eigentlichen Funktionen.
- Die Facade enthält keine Logik.
- Die Subklassen wissen jedoch nichts von der Facade.

**Eigenschaften**
- Vereinfacht Anwendung mehrere Subsysteme.
- Minimiert die Abhängigkeiten zu den Subsystemen. ([[VSK/Modularisierung/Kopplung|Kopplung]] minimieren.)
- Einfach Austauschbarkeit des Subsystems.

**Negativ**
- Kann schnell zum Durchlauferhitzer werden.

**Empfehlung**
- Gezielt zur Entkopplung einsetzen.
- Darf nie Logik enthalten.