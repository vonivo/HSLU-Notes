>[!Definition]
>Eine Strategy definiert eine Familie von Algorithmen, kapselt dabei jeden Algorithmus und macht diese Austauschbar. Durch die Stragtey wird der Client unabhängig von genutzten Algorithmus. (siehe [[Strategy-Pattern|PLAB Strategy]])
>- [[Behavioral-Patterns]]
>- [[Entwurfsmuster|Objektbasiert]]

![[strategy.png]]
In Java, wo keine Mehrfachvererbung existiert, werde [[Interface|Interfaces]] verwendet.
![[Strategy2.png]]

**Eigenschaften**
- **Kontext:** Optional, kann auch direkt durch Client erledigt werden.
	- Besitzt Referenz auf die konkrete Strategie
	- Stellt wennötig Datenschnittstelle für die Strategei zur Verfügung.
- **Konkrete Strategie**:
	- Konkrete Implementation eines z.B. Sortieralgorithmus.


**Vorteile**
- Anbieten von unterschiedlichen Varianten / Implementationen von Algorithmen.
- Eng verwante Klassen, die sich nur im Verhalten unterscheiden können zusammengefasst werden.
- Open-Closed Principle.

**Empfehlung**
- Leitch Unterschätzt.
- Kann sich auch bei kleinen Methoden lohnen.
