Um einen Prozess zu verwalten, muss das OS wissen, wo der Prozess abgelegt ist und was seine Attribute sind ([[Prozess Kontrol Block]])
![[Pasted image 20250107171913.png]]

Wird ein Prozess gewechselt, müssen folgende Schritte abgearbeitet werden:
1. Speicher den Prozesskontext
2. Ändere den Prozess-Kontrol-Block für den laufenden Prozess
3. Verschiebe den Prozess in die entsprechende [[Queuing Modell|Queue]]
4. Wähle einen neuen Prozess aus.
5. Ändere den [[Prozess Kontrol Block]] des neuen Blocks
6. Lade den Prozesskontext des neuen Blocks