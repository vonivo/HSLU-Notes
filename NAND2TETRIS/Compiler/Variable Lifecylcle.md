Der Lebenszyklus der Variablen ist in Jack wie folgt definiert:
- **Static**: Bleiben während der gesamten Programmausführung erhalten.
- **Field**: Bleiben erhalten, solange die Objekte nicht gelöscht werden.
- **Lokal & Argumente**: Nur während der Methoden Durchführung. Speicher wird nach Ausführung recycled.

Die Verwaltung der Lebenszyklen von Variablen ist eine grosse Herausforderung -> Die Semantik der [[Stack-Machine]] nimmt das aber komplett ab.

