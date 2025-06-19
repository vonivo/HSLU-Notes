>[!Definition]
>Ein **Observer** definiert eine Abhängigkeit zwischen einem Subjekt (Observable) dessen Zustände ändern können und einer Menge von Beobachter (Observer) die darüber informiert werden sollen.
>- [[Behavioral-Patterns]]
>- [[Entwurfsmuster|Objektbasiert]]

![[Observer.png]]

**Eigenschaften**:
-  Subjekt
	- Verwaltet seine Beobachter ($0\dots n$)
	- Biete Methoden zur An- und Abmeldung
- Beobachter
	- Definiert eine Benachrichtigungsschnittstelle
- Konkretes Subjet / Beobachter
	- Sendet und empfängt Aktualisierung


**Vorteile**
- Lose [[VSK/Modularisierung/Kopplung|Kopplung]] der Zuhörer.
- Anzahl der Observer variabel.
- Kommunikation entegen der Abhängigkeitsrichtung.
- Auflösung von zyklischen Referenzen.

## Java Implementation
![[JavaObserver.png]]
In Java wird das ganze durch Evnet Listener eleganter.

>[!warning]
>Bei Java sollte immer dieses Event/Listener-Modell verwendet werden, da es deutlich felixbler ist als das Observer-Pattern von der GoF.

