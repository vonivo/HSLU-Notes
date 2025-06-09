Das Zusammenspiel der [[Komponente|Komponenten]] wird durch einen **Vertrag** ([[Schnittstelle]]) erreicht.

- **Preconditions:** Zusicherungen, die der Aufrufer einzhalten hat.
- **Postconditions:** Nachbedingungen, die der Aufgerufene garantiert.
- **Invarianten**: Bedingungen, die Instanzen einer Klassen ab der Erzeugung erfüllen müssen.

Der Vertrag kann sich auf Variablen, Parameter und Objektzustände beziehen.

**Verantwortlichkeiten**

|               | Nutzer                                                        | Anbieter                                                        |
| ------------- | ------------------------------------------------------------- | --------------------------------------------------------------- |
| Precondition  | Nutzer stellt sicher, dass Bedingung erfüllt                  | Prüft., Aussagekräftige Meldungen falls inkorrekt               |
| Postcondition | Während Entwicklung:<br>Doppelcheck mittels Assert (defensiv) | Stellt sicher, dass Nachbedingung korrekt sind.                 |
| Invariante    |                                                               | Stellt sicher, dass Invariante vor- und nach Ausführung gelten. |
