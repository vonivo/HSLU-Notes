Eine `BlockingQueue`[[AD/Datenstrukturen/Datenstruktur|Datenstruktur]], welche [[Blockierender Aufruf|blockierende Aufrufe]] implementiert.

### Methoden
- `boolean offer(E e)`
- `boolean offer(E e, long timeout)` -> Versucht ein Element am Ende der Queue einzufügen.
	- Rückgabewert gibt an, ob das Element hinzugefügt wurde.
	- Die Variante mit dem Timeout wartet, wenn nötig auf einen freien Platz, bis das Timeout abgelaufen 
- `E poll()`
- `E poll(long timeout)` -> Entnimmt das erste Element aus der Queue, falls vorhanden, wenn kein Element verfügbar ist, wird `null` retourniert. Timeout gibt an, wie lange auf einen freien Platz gewartet werden soll.
- `void put(E e)` -> [[Blockierender Aufruf]]. Fügt ein Element der Queue hinzu und wartet, bis ein Platz dafür frei ist.
- `E take()` -> [[Blockierender Aufruf]]. Entnimmt das erste Element der Queue, wartete gegebenenfalls, bis ein Element verfügbar ist.