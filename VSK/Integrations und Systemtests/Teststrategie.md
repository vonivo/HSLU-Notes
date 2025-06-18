Mit keiner Testart findet man im [[Softwaretesting]] alle Fehler, nur im Zusammenwirken der unterschiedlichen Arten findet man ein Maximum an Fehler.


**Eigenschaften**
- **Fachgerecht**: Passende Testziele, Methodiken und Testarten.
- **Risikogerecht**: Nicht alle Software-Teile sind gleich kritisch und müssen gleich akribisch getestet werden.
- **Wirtschaftlich**: In der Regel existiert ein beschränktes Test-Budget.

**Dimensionen**
- **[[Qualitätskriterien des Produkts]]**:
- **[[Hierarchieebenen]]**: System, Service, Komponenten, Klassen, etc.
- **Automatisierung**: Nutzen im Verhältnis zum Ertrag.

## Vorgehen
Bei der Erstellung einer Teststrategie wird pro Ebene des [[C4-Modell]] ermittelt, ob getestet werden soll.
- Auf Systemebene wird **immer** getestet.

1. **Wie soll getestet werden**: Sollen einzelne Units und/oder mehrere Module im Verbund getestet werden
	- [[Unit Tests]] sind meist aufwändiger aber selektiver.
2. **Welche Qualitätskriterien sollen getestet werden**: Soll zusätzlich zu Funktionalität noch Benutzbarkeit, Zuverlässigkeit, etc. getestet werden?
3. **Automatisierung**: Wie oft werden Tests ausgeführt, soll getestet werden?